<template>
    <div>
        <div>
            <h1>Participants list ({{ participants.length }})</h1>
            <ol>
                <li v-for="person in participants" :key="person">
                    {{ person.name }} {{ person.surname }}
                </li>
            </ol>
        </div>
        <h3>New participant</h3>
        <form @submit.prevent="addNewParticipant()">
            <label>Firstname</label>
            <input type="text" v-model="newParticipant.name">
            <label>Lastname</label>
            <input type="text" v-model="newParticipant.surname">
            <button>Add new participant</button>
        </form>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                participants: [],
                newParticipant: {},
            };
        },
        methods: {
            addNewParticipant() {
                this.participants.push(this.newParticipant);
                this.newParticipant = {};
            }
        }
    };
</script>