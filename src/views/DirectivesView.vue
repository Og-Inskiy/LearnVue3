<template>
  <section class="m-4">

    <h3>Декларативная отрисовка</h3>
    <p>{{ message }}</p>

    <h3>Директива v-model</h3>
    <form class="form-control" action="#" method="POST">
      <input class="input-group m-2" v-model="login" type="text" name="login" value="" placeholder="Введите логин">
      <p class="m-2">Ваш логин: {{ login }}</p>
    </form>

    <h3>Директива v-if</h3>
    <div v-if="seen">
      <p>Этот блок виден, так как переменная seen - истина</p>
      <p>А второй блок не виден и убран из DOM-дерева</p>
    </div>
    <div v-if="!seen">
      <p>Второй блок</p>
    </div>

    <h3>Директива v-if</h3>
    <div v-show="seen">
      <p>Этот блок виден, так как переменная seen - истина</p>
      <p>А второй блок скрыт с помощью атрибута style="display: none;"</p>
    </div>
    <div v-show="!seen">
      <p>Второй блок</p>
    </div>
  </section>

  <h3>Директва v-for(массив)</h3>
  <div>
    <p>Список фруктов:</p>
    <ol>
      <li v-for="fruit in fruits">{{ fruit }}</li>
    </ol>
  </div>

  <h3>Директива v-for (массив объектов)</h3>
  <div>
    <p>Список студентов:</p>
    <ul>
      <li v-for="student in students">
        ФИО: <b>{{ student.fio }}</b><br />
        Дата рождения: {{ student.birth }} <br />
        Пол: {{ student.sex }}
      </li>
    </ul>
  </div>

  <h3>Директива v-bind</h3>
  <div>
    <img :class="{img:active}" v-bind:src="bind_img" v-bind:alt="bind_value" :title="bind_value">
  </div>

    </template>

<script>
export  default {
  data(){
    return {
      message: "Приветствую вас на курсе по изучению фреймворка Vue 3!",
      login: null,
      seen: true,
      fruits: ["Яблоко", "Апельсин","Банан","Груша"],
      students:[
        {
          fio: "Галацан Иван Павлович",
          birth: '22.05.2006',
          sex: "Мужской",
        },
        {
          fio: "Глазунов Иван Сергеевич",
          birth: '17.08.2006',
          sex: "Мужской",
        },
        {
          fio: "Огинский Иван Станиславович",
          birth: '29.03.2006',
          sex: "Мужской",
        }
      ],
      bind_img: 'https://img.freepik.com/free-photo/the-adorable-illustration-of-kittens-playing-in-the-forest-generative-ai_260559-483.jpg?size=338&ext=jpg&ga=GA1.1.632798143.1712707200&semt=ais',
      bind_value: 'Милый котик',
    }
  }
}




</script>


