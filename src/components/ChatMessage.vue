<template>

    <!-- To display both teacher and student messages from a single component, I've used a conditional that detects which user has sent the message, and then style accordingly -->

    <div v-if="item.author === 'student'" class="messages-wrapper">
      <div class="message-container">
        <p>
          <slot name="content"></slot>
        </p>
        <small>
          <slot name="date"></slot>
        </small>
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
        <p>
          <slot name="content"></slot>
        </p>
        <small>
          <slot name="date"></slot>
        </small>
      </div>
    </div>
  
</template>

<script>
export default {
  name: 'ChatMessage',
  props: ['item']
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
  margin-right: 1rem;
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

@media only screen and (max-width: 590px) {
  .thumbnail {
    display: none;
  }

  .message-container,
  .message-container2 {
    font-size: 0.9rem;
    max-width: 100%;
  }

}
</style>