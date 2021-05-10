<template>

  <div v-for="msg in messages" :key="msg">
    <div v-if="msg.value.author === 'student'" class="messages-wrapper">
      <div class="message-container">
        <p>{{ msg.value.content }}</p>
        <small>{{ msg.value.date }}</small>
      </div>
      <div class="thumbnail">
        <img src="@/assets/student-profile.jpeg" alt="Student's profile photo">
      </div>
    </div>
    <div v-else class="messages-wrapper2">
      <div class="thumbnail">
        <img src="@/assets/teacher-profile.jpeg" alt="Teacher's profile photo">
      </div>
      <div class="message-container2">
        <p>{{ msg.value.content }}</p>
        <small>{{ msg.value.date }}</small>
      </div>
    </div>
    
  </div>
  
</template>

<script>
export default {
  name: 'ChatMessage',
}
</script>

<style>
/* STUDENT MESSAGES */
.messages-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  gap: 1rem;
  margin: 1rem 0;
}
.message-container {
  text-align: right;
  background-color: rgb(56, 190, 231);
  padding: 0.5rem 1rem;
  max-width: 70%;
  border-radius: 0.5rem;
  color: white;
}

.thumbnail {
  max-width: 50px;
}

.thumbnail img {
  max-height: 30px;
  max-width: 35px;
  border-radius: 0.5rem;
}

/* TEACHER MESSAGES */
.messages-wrapper2 {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  gap: 1rem;
  margin: 1rem 0;
}
.message-container2 {
  text-align: left;
  background-color: rgb(246, 246, 246);
  padding: 0.5rem 1rem;
  max-width: 70%;
  border-radius: 0.5rem;
}
</style>