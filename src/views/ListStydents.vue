<template>
  <div class="list-container">
    <div class="table_rate">
      <h3>Ученики 1 "A" класса</h3>
      <el-table :data="students1">
        <el-table-column prop="fio" label="ФИО" />
        <el-table-column prop="classes" label="Класс" />
        <el-table-column v-if="userCondition">
        <el-table-column>
          <template slot-scope="scope">
            <el-button type="danger" size="small" @click="deleteStudent(scope.row)">Удалить</el-button>
          </template>
        </el-table-column>
      </el-table-column>
      </el-table>
    </div>
    <div class="table_rate">
      <h3>Ученики 2 "A" класса</h3>
      <el-table :data="students2">
        <el-table-column prop="fio" label="ФИО" />
        <el-table-column prop="classes" label="Класс" />
        <el-table-column v-if="userCondition">
        <el-table-column>
          <template slot-scope="scope">
            <el-button type="danger" size="small" @click="deleteStudent(scope.row)">Удалить</el-button>
          </template>
        </el-table-column>
      </el-table-column>
      </el-table>
    </div>
    <div class="table_rate">
      <h3>Ученики 3 "A" класса</h3>
      <el-table :data="students3">
        <el-table-column prop="fio" label="ФИО" />
        <el-table-column prop="classes" label="Класс" />
        <el-table-column v-if="userCondition">
        <el-table-column>
          <template slot-scope="scope">
            <el-button type="danger" size="small" @click="deleteStudent(scope.row)">Удалить</el-button>
          </template>
        </el-table-column>
        </el-table-column>
      </el-table>
    </div>
    <div class="table_rate">
      <h3>Ученики 4 "A" класса</h3>
      <el-table :data="students4">
        <el-table-column prop="fio" label="ФИО" />
        <el-table-column prop="classes" label="Класс" />
        <el-table-column v-if="userCondition">
        <el-table-column>
          <template slot-scope="scope">
            <el-button type="danger" size="small" @click="deleteStudent(scope.row)">Удалить</el-button>
          </template>
        </el-table-column>
        </el-table-column>
      </el-table>
    </div>
    <el-table-column v-if="userCondition">
    <div class="formAddShedule">
      <div class="form-container">
        <h2>Изменить</h2>
        <div class="form-row">
          <div class="input-group">
            <label for="fio">ФИО:</label>
            <input type="text" id="fio" v-model="newStudent.fio" />
          </div>
          <div class="input-group">
            <label for="classes">Класс:</label>
            <input type="text" id="classes" v-model="newStudent.classes" />
          </div>
        </div>
        <div class="form-row">
          <el-button type="success" @click="onSubmit">Добавить</el-button>
        </div>
      </div>
    </div>
    </el-table-column>
  </div>
</template>

<script>
import { store } from '../store/index'
export default {
  name: 'App',
  data() {
    return {
      newStudent: {
        fio: '',
        classes: '',
      }
    }
  },
  computed: {
    userCondition(){
      return store.state.user
    },
    students1() {
      return store.state.students.filter(student => student.classes === '1 класс')
    },
    students2() {
      return store.state.students.filter(student => student.classes === '2 класс')
    },
    students3() {
      return store.state.students.filter(student => student.classes === '3 класс')
    },
    students4() {
      return store.state.students.filter(student => student.classes === '4 класс')
    }
  },
  methods: {
    onSubmit() {
      const studentData = {
        fio: this.newStudent.fio,
        classes: this.newStudent.classes,
      }
      this.$store.dispatch('addStudent', studentData)
    },
    deleteStudent(scope) {
      store.dispatch('delStudent', scope.id)
    }
  }
}
</script>

<style>
.list-container {
  padding: 10px;
  height: 100vh; /* Установите желаемую высоту контейнера */
  overflow-y: auto; /* Включает вертикальный скроллинг */
}

.table_rate {
  background-color: #fff;
  margin: 20px;
}

.formAddShedule {
  margin: 20px;
}

.form-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  background-color: #fff;
  padding: 20px;
}

.form-row {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 1rem;
}

.input-group {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0.5rem;
  width: 100%;
}

input,
select {
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1rem;
  width: 100%;
}

@media (max-width: 768px) {
  .form-row {
    flex-direction: column;
  }

  .input-group {
    width: 100%;
  }

  input,
  select {
    width: 100%;
  }
}
</style>