<template>
  <div class="main">
    <div class="fist-column">
      <h1 class="fist-column__header">Добавление товара</h1>


        <h4 class="form__title" >Наименование товара</h4>
        <input
          class="form__input"
          type="text"
          placeholder="Введите наименование товара"
          v-model="title"
          required
        />
        <span class="form__error">Поле является обязательным</span>
        <h4 class="form__title">Описание товара</h4>
        <textarea
          class="form__area"
          type="text"
          placeholder="Введите описание товара"
          v-model="descr"
        ></textarea>
        <h4 class="form__title">Ссылка на изображение товара</h4>
        <input class="form__input" placeholder="Введите ссылку" v-model="link" type="text" />
        <span class="form__error">Поле является обязательным</span>
        <h4 class="form__title">Цена товара</h4>
        <input class="form__input"  placeholder="Введите цену" v-model="price"  type="number" min="1"/>
        <span class="form__error" >Поле является обязательным</span>
        <button :disabled="!title||!descr||!link||!price"  class="form__button" @click="say()" >Добавить товар</button>

    </div>
    <div class="second-column">
      <!-- <button class="button-sort">
        <p class="button-sort__text">По умолчанию</p>
        <img src="" />
      </button> -->
      <div class="cards">
        <!-- <div class="card">
          <div class="card__image"></div>
          <div class="card__text">
            <h2 class="card__title">Наименование товара</h2>
            <p class="card__descr">
              Довольно-таки интересное описание товара в несколько строк.
              Довольно-таки интересное описание товара в несколько строк
            </p>
            <h2 class="card__price">10 000 руб.</h2>
          </div>
          <div class="card__del"><img /></div>
        </div> -->
      </div>
    </div>
  </div>
</template>

<style >
* {
  box-sizing: border-box;
  font-family: Source Sans Pro, Arial, Helvetica, sans-serif;
  font-style: normal;
  font-weight: normal;
  margin: 0;
  padding: 0;
}

.main {
  max-width: 1440px;
  margin: auto;
  display: flex;
  background: rgba(255, 254, 251, 0.8);
}

.fist-column {
  max-width: 320px;
  display: flex;
  flex-direction: column;
  margin: 32px 16px 0 32px;
}

.fist-column__header {
  font-weight: 600;
  font-size: 28px;
  line-height: 35px;
  color: #3f3f3f;
}

.form {
  width: 332px;
  height: 440px;
  display: flex;
  flex-direction: column;
  margin-top: 16px;
  padding: 24px;
  background: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
}

.form__title {
  height: 13px;
  margin-bottom: 4px;
  margin-top: 16px;
  font-size: 10px;
  line-height: 13px;
  letter-spacing: -0.02em;
  color: #49485e;
}

.form__title:first-child {
  margin-top: 32px;
}

.form__title::after {
  content: "";
  width: 4px;
  height: 4px;
  background: #ff8484;
  border-radius: 4px;
}

.form__input {
  height: 36px;
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border: none;
  border-radius: 4px;
}

span {
  margin-top: 4px;
  font-size: 8px;
  line-height: 10px;
  letter-spacing: -0.02em;
  color: #ff8484;
}

.form__area {
  height: 108px;
  margin-bottom: 16px;
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border: none;
  border-radius: 4px;
}

::placeholder {
  padding: 10px 0 11px 16px;
  font-size: 12px;
  line-height: 15px;
  color: #b4b4b4;
}

.form__button {
  height: 36px;
  margin-top: 8px;
  background: #eeeeee;
  border: none;
  border-radius: 10px;
  font-size: 12px;
  line-height: 15px;
  text-align: center;
  letter-spacing: -0.02em;
  color: #b4b4b4;
  cursor: pointer;
}

.form__button_ok {
  background: #7bae73;
  color: #ffffff;
}

.second-column {
  width: 100%;
  margin-top: 31px;
  display: flex;
  flex-direction: column;
}

.button-sort {
  width: 121.49px;
  height: 36px;
  display: flex;
  flex-direction: row;
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border: none;
  border-radius: 4px;
  margin-left: auto;
  margin-right: 32px;
}

.button-sort__text {
  padding: 10px 0 11px 16px;
  font-size: 12px;
  line-height: 15px;
  color: #b4b4b4;
}

.cards {
  margin-top: 16px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px;
}

.card {
  position: relative;
      height: 350px;
    width: 300px;
  display: flex;
  flex-direction: column;
  background: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  border: 1px solid red;
}

.card__image {
  background: url();
  width: 100%;
  height: 200px;
}

.card__text {
  padding: 16px;
}

.card__title {
  margin-bottom: 16px;
  font-weight: 600;
  font-size: 20px;
  line-height: 25px;
  color: #3f3f3f;
}

.card__descr {
  margin-bottom: 32px;
  font-size: 16px;
  line-height: 20px;
  color: #3f3f3f;
}

.card__price {
  font-weight: 600;
  font-size: 24px;
  line-height: 30px;
  color: #3f3f3f;
}
.card__del {
  position: absolute;
  right: -8px;
  top: -8px;
  cursor: pointer;
  width: 32px;
  height: 32px;
  background: #ff8484;
  background-image: url('trash.svg');
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  background-repeat: no-repeat;
    background-position: center;
}

.form__error {
  display: none;
}

.form__input:valid:not(:placeholder-shown) {
	border-color: #ffdb4d;
}

.form__input:invalid:not(:placeholder-shown) {
	border-color: #df4b41;
}

.form__input:invalid:not(:placeholder-shown) + .form__error {
	display: block;
}

.form__button:not(:disabled) {
  background-color: #064f8b;
  color: red;
}


@media screen and (max-width:1024px) {
  .main {flex-direction: column;
    align-items: center;
  }

  .cards {
    margin-top: 16px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
  }

  .fist-column {
    margin: 32px 32px;
  }
}

@media screen and (max-width: 350px) {
  .fist-column {
    margin: 0;
  }
}
</style>



<script>
export default {
  data() {
        return {
            title: '',
            link: '',
            descr: '',
            price: '',
        };
  },
  methods: {
    say: function () {
      const cards = document.querySelector('.cards');
      const card = document.createElement('div');
      const img = document.createElement('img');
      const title = document.createElement('h3');
      const description = document.createElement('p');
      const price = document.createElement('p');
      const del = document.createElement('div');

      card.classList.add('card');
      img.classList.add('card__image');
      title.classList.add('card__title');
      description.classList.add('card__descr');
      price.classList.add('card__price');
      del.classList.add('card__del');

    img.src = this.link;
    title.textContent = this.title;
    description.textContent = this.descr;
    price.textContent = this.price + ' rub';
    //https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Cat03.jpg/240px-Cat03.jpg


      card.appendChild(img);
      card.appendChild(title);
      card.appendChild(description);
      card.appendChild(price);
      card.appendChild(del);
      cards.appendChild(card);
      function lol() {
      let del = document.querySelector('.card__del')
      console.log(del, 'fgfgfgfgfgfgfg')
      // del.addEventlistener('click', () => {alert('loh')})
    let dels = document.querySelectorAll('.card__del')
    console.log(dels)
    for(let el of dels) {
      el.addEventListener('click', () => {
        console.log('lol')
        el.parentElement.remove(el)

      })
    }
    }

    lol()
    },
  validErr: function () {
    const validationErrors = {
    noValue: "Это обязательное поле",
    range: "Должно быть от 2 до 30 символов",
    link: "Здесь должна быть ссылка",
  };
  }
  }

}
</script>


// pattern="http(s)?:\/\/(www\.)?(((([a-z]+(-[a-z]+)+)|([a-z]{2,}))(\.[a-z]{2,6})+)|(([1-9]|([1-9]\d)|(1\d\d)|(2[1-4]\d)|(25[0-5]))(\.([0-9]|([1-9]\d)|(1\d\d)|(2[0-4]\d)|(25[0-5]))){2}\.([1-9]|([1-9]\d)|(1\d\d)|(2[1-4]\d)|(25[0-5]))))((:(([1-9]\d)|([1-9]\d\d)|([1-9]\d\d\d)|([1-9]\d\d\d\d)))?)((/[a-z]{2,})*(#)?)"
