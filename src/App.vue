<script>
export default {
  name: "App",
  data() {
    return {
      cards: [
        {
          status: 0,
          title: "Neue Aufgaben",
          bgColor: "danger",
          newTask: true,
        },
        {
          status: 1,
          title: "In Bearbeitung",
          bgColor: "primary",
          newTask: false,
        },
        {
          status: 2,
          title: "Erledigt",
          bgColor: "success",
          newTask: false,
        },
      ],
      tasks: [
        {
          id: 1,
          content: "Dashboard überarbeiten.",
          status: 0,
        },
        {
          id: 2,
          content: "Anwendung auf Vue.js umstellen.",
          status: 0,
        },
        {
          id: 3,
          content: "Lorem ipsum dolor sit amet.",
          status: 1,
        },
        {
          id: 4,
          content: "Lorem ipsum dolor.",
          status: 2,
        },
        {
          id: 5,
          content: "Lorem ipsum sit amet.",
          status: 2,
        },
        {
          id: 6,
          content: "Lorem, ipsum.",
          status: 2,
        },
        {
          id: 7,
          content: "Kein Internet...",
          status: 1,
        },
      ],
    };
  },
  computed: {
    newTasks() {
      return this.tasks.filter((task) => task.status === 0);
    },
  },
};
</script>
<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-4">
        <div class="card">
          <div class="card-header text-center bg-secondary text-white">
            <h4>Neue Aufgaben</h4>
          </div>
          <div class="card-body">
            <div
              class="alert alert-secondary"
              v-for="task in newTasks"
              :key="task.id"
            >
              {{ task.content }}
            </div>
          </div>
          <div class="card-footer">
            <input
              type="text"
              class="form-control"
              placeholder="Neue Aufgabe"
            />
            <div class="d-grid my-2">
              <button class="btn btn-secondary">Eintragen</button>
            </div>
          </div>
        </div>
      </div>
      <div class="col-4">
        <div class="card">
          <div class="card-header text-center bg-primary text-white">
            <h4>In Bearbeitung</h4>
          </div>
          <div class="card-body"></div>
        </div>
      </div>
      <div class="col-4">
        <div class="card">
          <div class="card-header text-center bg-success text-white">
            <h4>Erledigt</h4>
          </div>
          <div class="card-body"></div>
        </div>
      </div>
    </div>
  </div>
</template>


