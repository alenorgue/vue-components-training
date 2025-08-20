<script setup>
import IdCard from './components/IdCard.vue'
import Random from './components/Random.vue'
import BoxColor from './components/BoxColor.vue'
import CreditCard from './components/CreditCard.vue'
import Rating from './components/Rating.vue'
import DriverCard from './components/DriverCard.vue'
import LikeButton from './components/LikeButton.vue'
import ClickablePicture from './components/ClickablePicture.vue'
import Dice from './components/Dice.vue'
import Carousel from './components/Carousel.vue'
import NumbersTable from './components/NumbersTable.vue'
import FaceBook from './components/FaceBook.vue'
import SignupPage from './components/SignupPage.vue'
</script>

<template>
  <h1>Creación de componentes con Vue</h1>
  <p>Crea a conitnuación todos los componentes del ejercicio.</p>
      <h1>1- ID Cards</h1>
<div>
  <IdCard
    picture="https://randomuser.me/api/portraits/men/44.jpg"
    first-name="John"
    last-name="Doe"
    gender="male"
    :height="178"
  :birth="new Date('1992-07-14')"
  />
 <IdCard
  last-name='Delores '
  first-name='Obrien'
  gender='female'
  :height="172"
  :birth='new Date("1988-05-11")'
  picture="https://randomuser.me/api/portraits/women/44.jpg"
/>
</div>
  <h1>2- Random number</h1>
<div>
  <Random :min="1" :max="6" />
  <Random :min="1" :max="100" />
</div>
<h1> 3- BoxColor</h1>
<div>
  <BoxColor :r="255" :g="0" :b="0" />
  <BoxColor :r="128" :g="255" :b="0" />

</div>
<h1> 4- Credit Card</h1>
<div class="creditcard-container">
    <CreditCard
      type="Visa"
      number="0123456789018845"
      :expiration-month="3"
      :expiration-year="2021"
      bank="BNP"
      owner="Maxence Bouret"
      bg-color="#11aa99"
      color="white"
    />
       <CreditCard
      type="Master Card"
      number="0123456789010995"
      :expiration-month="3"
      :expiration-year="2021"
      bank="N26"
      owner="Maxence Bouret"
      bg-color="#eeeeee"
      color="#222222"
    />

    <CreditCard
      type="Visa"
      number="0123456789016984"
      :expiration-month="12"
      :expiration-year="2019"
      bank="Name of the Bank"
      owner="Firstname Lastname"
      bg-color="#ddbb55"
      color="white"
    />
</div>
<h1> 5- Rating</h1>
<div>
    <Rating :rate="0" />
    <Rating :rate="1.49" />
    <Rating :rate="1.5" />
    <Rating :rate="3" />
    <Rating :rate="4" />
    <Rating :rate="5" />
</div>
<h1> 6- Driver Card</h1>
<div>
  <DriverCard
      name="Travis Kalanick"
      :rating="4.2"
      img="https://si.wsj.net/public/resources/images/BN-TY647_37gql_OR_20170621052140.jpg?width=620&height=428"
      :car="{ model: 'Toyota Corolla Altis', licensePlate: 'CO42DE' }"
    />
    <DriverCard
      name="Dara Khosrowshahi"
      :rating="4.9"
      img="https://ubernewsroomapi.10upcdn.com/wp-content/uploads/2017/09/Dara_ELT_Newsroom_1000px.jpg"
      :car="{ model: 'Audi A3', licensePlate: 'BE33ER' }"
    />
</div>
<h1> 7- Like Button</h1>
<div>
  <LikeButton />
  <LikeButton />
</div>
<h1> 8- Clickable Picture</h1>
<div>
  <ClickablePicture img="maxence.png" img-clicked="maxence-glasses.png" />
</div>
<h1> 9- Dice</h1>
<div>
  <Dice />
</div>
<h1>10- Carousel</h1>
<div>
<Carousel
  :images="[
    'https://randomuser.me/api/portraits/women/1.jpg',
    'https://randomuser.me/api/portraits/men/1.jpg',
    'https://randomuser.me/api/portraits/women/2.jpg',
    'https://randomuser.me/api/portraits/men/2.jpg'
  ]"
/>
</div>
<h1>11- Numbers Table</h1>
<div>
<NumbersTable :limit="50" />
</div>
<h1> 12- FaceBook</h1>
<div>
<FaceBook />
</div>
<h1>14- Sign up Page</h1>
<SignupPage />
</template>

<style scoped>
h2 {margin: 1rem 0;}
 .creditcard-container {
  border: solid white 2px;
  margin: 1rem;
    padding: 1rem;
    color: white;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
 }
</style>
 