<template>
    <div class="modal" v-if="show">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">{{ title }}</h5>
            <button type="button" class="close" @click="$emit('close')">
              <span>&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <table>
              <thead>
                <tr>
                  <th>Name</th>
                  <th>Age</th>
                  <th>Email</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(user, index) in users" :key="index">
                  <td>{{ user.name }}</td>
                  <td>{{ user.age }}</td>
                  <td>{{ user.email }}</td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" @click="$emit('close')">
              Close
            </button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Modal',
    props: {
      title: {
        type: String,
        default: 'Modal Title',
      },
      show: {
        type: Boolean,
        default: true,
      },
      users: {
        type: Array,
        default: () => [],
      },
    },
  };
  </script>
  
  <style scoped>
  .modal {
    position: fixed;
    z-index: 999;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .modal-dialog {
    width: 90%;
    max-width: 800px;
    background-color: #fff;
    border-radius: 5px;
  }
  
  .modal-content {
    padding: 20px;
  }
  
  .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .modal-title {
    margin: 0;
  }
  
  .close {
    border: none;
    background-color: transparent;
    font-size: 24px;
    font-weight: bold;
    color: #000;
    cursor: pointer;
  }
  
  .close:focus,
  .close:hover {
    color: #999;
    text-decoration: none;
    outline: none;
  }
  
  .modal-body {
    padding: 20px 0;
  }
  
  table {
    width: 100%;
    border-collapse: collapse;
  }
  
  th,
  td {
    padding: 10px;
    border: 1px solid #ddd;
    text-align: left;
  }
  
  th {
    background-color: #f2f2f2;
    font-weight: bold;
  }
  </style>
  