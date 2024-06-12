<template>
    <div class="homework-container">
      <h1>Домашние задания</h1>
      
      <div class="table_homework">
        <h3>Домашнее задание для 1 "А" класса</h3>
        <el-table :data="sortedHomeworkClass1">
          <el-table-column prop="date" label="Дата" :formatter="formatDate" />
          <el-table-column prop="them" label="Тема" />
          <el-table-column prop="task" label="Задание" />
          <el-table-column prop="deadline" label="Дата проверки" :formatter="formatDate" />
          <el-table-column v-if="userCondition">
              <template slot-scope="scope">
                <el-button type="danger" size="small" @click="deleteHW(scope.row)">выполнено</el-button>
              </template>
          </el-table-column>
        </el-table>
        
        <div class="formHhomework" v-if="userCondition">
          <h3>Добавить домашнее задание для 1"А" класса</h3>
          <div class="form-row">
            <div class="input-group">
              <label for="date">Дата</label>
              <el-date-picker
                v-model="addHomeWorkClass1.date"
                type="date"
                placeholder="гггг.мм.дд"
                :first-day-of-week="2">
              </el-date-picker>
            </div>
          </div>
          <div class="form-row">
            <div class="input-group">
              <label for="them">Тема</label>
              <input type="text" id="wednesday" v-model="addHomeWorkClass1.them" />
            </div>
            <div class="input-group">
              <label for="task">Задание</label>
              <input type="text" id="wednesday" v-model="addHomeWorkClass1.task" />
            </div>
          </div>
          <div class="form-row">
            <div class="input-group">
              <label for="task">Дата проверки</label>
              <el-date-picker
                v-model="addHomeWorkClass1.deadline"
                type="date"
                placeholder="гггг.мм.дд"
                :first-day-of-week="2">
              </el-date-picker>
            </div>
          </div>
          
          <div class="input-group">
            <el-button type="success" @click="onSubmitClass1()">Добавить</el-button>
          </div>
        </div>
      </div>
  
      <div class="table_homework">
        <h3>Домашнее задание для 2"А" класса</h3>
        <el-table :data="sortedHomeworkClass2">
          <el-table-column prop="date" label="Дата" :formatter="formatDate" />
          <el-table-column prop="them" label="Тема" />
          <el-table-column prop="task" label="Задание" />
          <el-table-column prop="deadline" label="Дата проверки" :formatter="formatDate" />
          <el-table-column v-if="userCondition">
              <template slot-scope="scope">
                <el-button type="danger" size="small" @click="deleteHW(scope.row)">выполнено</el-button>
              </template>
          </el-table-column>
        </el-table>
        
        <div class="formHhomework" v-if="userCondition">
          <h3>Добавить домашнее задание для 2"А" класса</h3>
          <div class="form-row">
            <div class="input-group">
              <label for="date">Дата</label>
              <el-date-picker
                v-model="addHomeWorkClass2.date"
                type="date"
                placeholder="гггг.мм.дд"
                :first-day-of-week="2">
              </el-date-picker>
            </div>
          </div>
          <div class="form-row">
            <div class="input-group">
              <label for="them">Тема</label>
              <input type="text" id="wednesday" v-model="addHomeWorkClass2.them" />
            </div>
            <div class="input-group">
              <label for="task">Задание</label>
              <input type="text" id="wednesday" v-model="addHomeWorkClass2.task" />
            </div>
          </div>
          <div class="form-row">
            <div class="input-group">
              <label for="task">Дата проверки</label>
              <el-date-picker
                v-model="addHomeWorkClass2.deadline"
                type="date"
                placeholder="гггг.мм.дд"
                :first-day-of-week="2">
              </el-date-picker>
            </div>
          </div>
          
          <div class="input-group">
            <el-button type="success" @click="onSubmitClass2()">Добавить</el-button>
          </div>
        </div>
      </div>
  
      <div class="table_homework">
        <h3>Домашнее задание для 3 "А" класса</h3>
        <el-table :data="sortedHomeworkClass3">
          <el-table-column prop="date" label="Дата" :formatter="formatDate" />
          <el-table-column prop="them" label="Тема" />
          <el-table-column prop="task" label="Задание" />
          <el-table-column prop="deadline" label="Дата проверки" :formatter="formatDate" />
          <el-table-column v-if="userCondition">
              <template slot-scope="scope">
                <el-button type="danger" size="small" @click="deleteHW(scope.row)">выполнено</el-button>
              </template>
          </el-table-column>
        </el-table>
        
        <div class="formHhomework" v-if="userCondition">
          <h3>Добавить домашнее задание для 3"А" класса</h3>
          <div class="form-row">
            <div class="input-group">
              <label for="date">Дата</label>
              <el-date-picker
                v-model="addHomeWorkClass3.date"
                type="date"
                placeholder="гггг.мм.дд"
                :first-day-of-week="2">
              </el-date-picker>
            </div>
          </div>
          <div class="form-row">
            <div class="input-group">
              <label for="them">Тема</label>
              <input type="text" id="wednesday" v-model="addHomeWorkClass3.them" />
            </div>
            <div class="input-group">
              <label for="task">Задание</label>
              <input type="text" id="wednesday" v-model="addHomeWorkClass3.task" />
            </div>
          </div>
          <div class="form-row">
            <div class="input-group">
              <label for="task">Дата проверки</label>
              <el-date-picker
                v-model="addHomeWorkClass3.deadline"
                type="date"
                placeholder="гггг.мм.дд"
                :first-day-of-week="2">
              </el-date-picker>
            </div>
          </div>
          
          <div class="input-group">
            <el-button type="success" @click="onSubmitClass3()">Добавить</el-button>
          </div>
        </div>
      </div>
  
      <div class="table_homework">
        <h3>Домашнее задание для 4 "А" класса</h3>
        <el-table :data="sortedHomeworkClass4">
          <el-table-column prop="date" label="Дата" :formatter="formatDate" />
          <el-table-column prop="them" label="Тема" />
          <el-table-column prop="task" label="Задание" />
          <el-table-column prop="deadline" label="Дата проверки" :formatter="formatDate" />
          <el-table-column v-if="userCondition">
              <template slot-scope="scope">
                <el-button type="danger" size="small" @click="deleteHW(scope.row)">выполнено</el-button>
              </template>
          </el-table-column>
        </el-table>
        
        <div class="formHhomework" v-if="userCondition">
          <h3>Добавить домашнее задание для 4"А" класса</h3>
          <div class="form-row">
            <div class="input-group">
              <label for="date">Дата</label>
              <el-date-picker
                v-model="addHomeWorkClass4.date"
                type="date"
                placeholder="гггг.мм.дд"
                :first-day-of-week="2">
              </el-date-picker>
            </div>
          </div>
          <div class="form-row">
            <div class="input-group">
              <label for="them">Тема</label>
              <input type="text" id="wednesday" v-model="addHomeWorkClass4.them" />
            </div>
            <div class="input-group">
              <label for="task">Задание</label>
              <input type="text" id="wednesday" v-model="addHomeWorkClass4.task" />
            </div>
          </div>
          <div class="form-row">
            <div class="input-group">
              <label for="task">Дата проверки</label>
              <el-date-picker
                v-model="addHomeWorkClass4.deadline"
                type="date"
                placeholder="гггг.мм.дд"
                :first-day-of-week="2">
              </el-date-picker>
            </div>
          </div>
          
          <div class="input-group">
            <el-button type="success" @click="onSubmitClass4()">Добавить</el-button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import {store} from '../store/index.js'
  export default {
    data(){
      return{
        addHomeWorkClass1: {
          date: null,
          them: '',
          task: '',
          deadline: null,
          class: 1
        },
        addHomeWorkClass2: {
          date: null,
          them: '',
          task: '',
          deadline: null,
          class: 2
        },
        addHomeWorkClass3: {
          date: null,
          them: '',
          task: '',
          deadline: null,
          class: 3
        },
        addHomeWorkClass4: {
          date: null,
          them: '',
          task: '',
          deadline: null,
          class: 4
        },
      }
    },
    computed:{
      userCondition(){
        return store.state.user
      },
  
  
      sortedHomeworkClass1() {
        return [...store.state.homework.filter(hw => hw.class === 1)].sort((a, b) => {
          return a.date.seconds - b.date.seconds;
        });
      },
      sortedHomeworkClass2() {
        return [...store.state.homework.filter(hw => hw.class === 2)].sort((a, b) => {
          return a.date.seconds - b.date.seconds;
        });
      },
      sortedHomeworkClass3() {
        return [...store.state.homework.filter(hw => hw.class === 3)].sort((a, b) => {
          return a.date.seconds - b.date.seconds;
        });
      },
      sortedHomeworkClass4() {
        return [...store.state.homework.filter(hw => hw.class === 4)].sort((a, b) => {
          return a.date.seconds - b.date.seconds;
        });
      }
    },
    methods:{
      onSubmitClass1() {
        this.$store.dispatch('addHomeWork', this.addHomeWorkClass1)
        this.addHomeWorkClass1 = {
          date: null,
          them: '',
          task: '',
          deadline: null,
          class: 1
        }
      },
      onSubmitClass2() {
        this.$store.dispatch('addHomeWork', this.addHomeWorkClass2)
        this.addHomeWorkClass2 = {
          date: null,
          them: '',
          task: '',
          deadline: null,
          class: 2
        }
      },
      onSubmitClass3() {
        this.$store.dispatch('addHomeWork', this.addHomeWorkClass3)
        this.addHomeWorkClass3 = {
          date: null,
          them: '',
          task: '',
          deadline: null,
          class: 3
        }
      },
      onSubmitClass4() {
        this.$store.dispatch('addHomeWork', this.addHomeWorkClass4)
        this.addHomeWorkClass4 = {
          date: null,
          them: '',
          task: '',
          deadline: null,
          class: 4
        }
      },
      formatDate(row, column, cellValue) {
        const date = new Date(cellValue.seconds * 1000); // Convert seconds to milliseconds
        return `${date.getDate()}.${date.getMonth() + 1}.${date.getFullYear().toString().slice(-2)}`;
      },
      deleteHW(row) {
        const hwToDelete = store.state.homework.find(hw => hw.id === row.id);
        if (hwToDelete) {
          this.$store.dispatch('delHomeWork', hwToDelete.id);
        }
      }
    }
  }
  </script>
  
  <style>
  .table_homework {
    background-color: #fff;
    width: 79vw;
    margin: 20px;
    padding: 10px;
  }
  
  .homework-container {
    height: 100vh;
    overflow-y: auto;
    width: 100%;
    padding-bottom: 10vh;
  }
  
  .homework-content {
    padding: 20px 0; /* Добавляет отступы для лучшего отображения */
  }
  
  .formHhomework {
    margin: 20px;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    background-color: #fff;
    padding: 20px;
  }
  
  .form-row {
    display: flex;
    width: 60vw;
    align-items: center;
    gap: 1rem;
    flex-direction: row;
  }
  
  .input-group {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }
  
  input,
  select {
    width: 20vmax;
    padding: 0.5rem;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 1rem;
  }
  
  @media (max-width: 768px) {
    .form-row {
      flex-direction: column;
      align-items: flex-start;
    }
    input,
    select {
      padding: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 1rem;
      width: 100%; /* Установите ширину на 100% для мобильных устройств */
    }
  }
  </style>