<template>
    <div>
        <div v-for="column in columns" :key="column.id">
            <header>
                {{ column.title }}
            </header>
            <p v-for="task in column.tasks" :key="task.id">
                {{  task.title }}
            </p>
        </div>
    </div>
</template>

<script setup lang="ts">
import { nanoid } from 'nanoid';
import type { Column } from '../types/index.ts';

const columns = ref<Column[]>([
    {
        id: nanoid(),
        title: "Backlog",
        tasks:[
            {
                id: nanoid(),
                title: 'Create marking landing page',
                createdAt: new Date(),
            },
            {
                id: nanoid(),
                title: 'Develop cool new feature',
                createdAt: new Date(),
            },
            {
                id: nanoid(),
                title: 'Fix page nav bug',
                createdAt: new Date(),
            }
        ]
        
    },
    {
        id: nanoid(),
        title: "Selected for Dev",
        tasks:[]
        
    },
    {
        id: nanoid(),
        title: "In Progress for Dev",
        tasks:[]
        
    }
])

</script>

