<template>
  <div class="main">
    <div class="main__fist-column">
      <h3 class="main__fist-column-heading">Добавление товара</h3>
      <div class="main__fist-column-item">
        <h6 class="main__fist-column-title">Наименование товара</h6>
        <input type="text" placeholder="Введите наименование товара">
        <h6 class="main__fist-column-description">Описание товара</h6>
        <input type="text" placeholder="Введите описание товара">
        <h6 class="main__fist-column-img">Ссылка на изображение товара</h6>
        <input type="text" placeholder="Введите ссылку">
        <h6 class="main__fist-column-price">Цена товара</h6>
        <input type="text" placeholder="Введите цену">
        <button class="button" @click="say('hi')">Добавить товар</button>
      </div>
    </div>
    <div class="main__second-column">

    </div>
  </div>
</template>

<style>

.main {
  display: flex;
  height: 100vh;
  border: 1px solid red;
  padding: 32px;
  margin: 0;
  box-sizing: border-box;
}

.main__fist-column {
  display: flex;
  flex-direction: column;
  height: 100%;
  width: 332px;
  border: 1px solid red;
}

.main__second-column {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  height: 100%;
  gap: 16px;
  width: 100%;
  border: 1px solid red;
}

.main__fist-column-heading {
  margin: 0;
  padding: 0;
  font-family: Source Sans Pro;
font-style: normal;
font-weight: 600;
font-size: 28px;
line-height: 35px;

color: #3F3F3F;
}

.main__fist-column-item {
  display: flex;
  flex-direction: column;
  margin-top: 16px;
  padding: 24px;
  width: 332px;
  height: 440px;
  border: 1px solid red;
  box-sizing: border-box;

background: #FFFEFB;
box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
border-radius: 4px;
}

.main__fist-column-title {

font-family: Source Sans Pro;
font-style: normal;
font-weight: normal;
font-size: 10px;
line-height: 13px;
/* identical to box height */
letter-spacing: -0.02em;

/* Temp / Darks / Lesser */
color: #49485E;
}
.main__fist-column-description {

font-family: Source Sans Pro;
font-style: normal;
font-weight: normal;
font-size: 10px;
line-height: 13px;
/* identical to box height */
letter-spacing: -0.02em;

/* Temp / Darks / Lesser */
color: #49485E;
}

.main__fist-column-img {

font-family: Source Sans Pro;
font-style: normal;
font-weight: normal;
font-size: 10px;
line-height: 13px;
/* identical to box height */
letter-spacing: -0.02em;

/* Temp / Darks / Lesser */
color: #49485E;
}

.main__fist-column-price {

font-family: Source Sans Pro;
font-style: normal;
font-weight: normal;
font-size: 10px;
line-height: 13px;
/* identical to box height */
letter-spacing: -0.02em;

/* Temp / Darks / Lesser */
color: #49485E;
}

.main__second-column-card{
  width: 332px;
  height: 423px;
  border: 1px solid red;
}

.main__second-column-card-img {
  width: 100%;
  height: 200px;
}

.main__second-column-card-description {
  width: 300px;
  height: 80px;
}



</style>



<script>
export default {
  methods: {
    say: function (message) {
      const cards = document.querySelector('.main__second-column');
      const card = document.createElement('div');
      const img = document.createElement('img');
      const title = document.createElement('h3');
      const description = document.createElement('p');
      const price = document.createElement('p');




      card.classList.add('main__second-column-card');
      img.classList.add('main__second-column-card-img');
      title.classList.add('main__second-column-card-title');
      description.classList.add('main__second-column-card-description');
      price.classList.add('main__second-column-card-price');

    img.src = 'https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Cat03.jpg/240px-Cat03.jpg';
    title.textContent = 'lolololol';
    description.textContent = 'lolololollololol ollolololollolololollololololl olololollolololollolololol';
    price.textContent = '100500';

      alert(message);
      card.appendChild(img);
      card.appendChild(title);
      card.appendChild(description);
      card.appendChild(price);
      cards.appendChild(card);
    }
  }
}
</script>
