<template>
  <div class="centered-container">
    <div class="valentine-container">
      <div v-if="yesPressed">
        <img
          src="https://i.pinimg.com/originals/58/77/c1/5877c185238a28d3305a5421933f8c3a.gif"
        />
        <div class="text-container">
          😇Тиймээ😇<br />
          Орой 6с шүү😘
        </div>
      </div>
      <div v-else>
        <img
          style="width: 400px; height: 240px"
          src="https://www.icegif.com/wp-content/uploads/2024/01/icegif-901.gif"
        />
        <h1 class="text-container">Надтай орой болзох уу?</h1>
        <div class="button-container">
          <button
            class="yes-button cursor-pointer"
            :style="`font-size: ${yesButtonSize()}px`"
            @click="setYesPressed(true)"
          >
            Тийм
          </button>

          <button
            @click="increaseNoCount()"
            class="no-button cursor-pointer"
          >
            {{ noCount === 0 ? 'Үгүй' : getNoButtonText() }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      yesPressed: false,
      noCount: 0,
      phrases: [
        'Үгүй',
        'Итгэлтэй байна уу?',
        'Үнэхээр итгэлтэй байна уу?',
        'Дахиад бодоод үзэлдээ!',
        'За сүүлийн боломж!',
        'Надаараа тоглоол?',
        'Битий даажигнаад байлдаа!',
        'Үнэхээр үгүй гэж үү?',
        'Харамсавдаа!',
        'Дахиад бодоод үз!',
        'Нээрээ үгүй гэж үү?',
        'Бүүр ингэж байнуу тэ!',
        'Сүүлийн хариулт чинь мөнүү?',
        'За яах вээ чамаар шалаа угаалгахаа мэдье !',
        'Шалны алчуураа бэлдээдэхье ;('
      ]
    };
  },
  methods: {
    setYesPressed(value) {
      this.yesPressed = value;
    },
    increaseNoCount() {
      console.log('noCount', this.noCount);
      this.noCount++;
    },
    yesButtonSize() {
      return this.noCount * 20 + 16;
    },
    getNoButtonText() {
      return this.phrases[Math.min(this.noCount, this.phrases.length - 1)];
    }
  }
};
</script>

<style scoped>
.centered-container {
  font-size: large;
  font-family: 'Times New Roman', Times, serif;
  flex-direction: column;
  align-items: right;
  justify-content: right;
  height: 100vh;
  width: 100vw;
  margin: 0;
}
.valentine-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
}
.button-container {
  display: flex;
  justify-content: center;
  align-items: center;
}
/* Custom class for Yes button styles */
.yes-button {
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  background-color: #a7efb8; /* bg-green-500 */
  color: #fff; /* text-white */
  font-weight: bold; /* font-bold */
  padding: 8px 16px; /* py-2 px-4 */
  border-radius: 8px; /* rounded */
  margin-right: 8px; /* mr-4 */
}

.yes-button:hover {
  background-color: #4f7457; /* hover:bg-green-700 */
}

/* Custom class for No button styles */
.no-button {
  background-color: #c90d0d; /* bg-red-500 */
  color: #fff; /* text-white */
  font-weight: bold; /* font-bold */
  padding: 8px 16px; /* py-2 px-4 */
  border-radius: 8px; /* rounded */
}

.no-button:hover {
  background-color: #c82333; /* hover:bg-red-700 */
}
/* Custom class for text-4xl my-4 container */
.text-container {
  font-size: 2.25rem; /* Equivalent to text-4xl in tailwindcss */
  margin-top: 1rem; /* Equivalent to my-4 in tailwindcss */
  margin-bottom: 1rem; /* Equivalent to my-4 in tailwindcss */
  text-align: center;
}

.github-link {
  position: absolute;
  top: 10px;
  left: 10px;
  color: #007bff; /* Set the color as needed */
  text-decoration: none;
}
/*scroll bar starts*/
*::-webkit-scrollbar {
  height: 10px;
  width: 10px;
}
*::-webkit-scrollbar-track {
  border-radius: 5px;
  background-color: #dce7e1;
  border: 6px double #ffffff;
}

*::-webkit-scrollbar-track:hover {
  background-color: #fcc5df;
}

*::-webkit-scrollbar-track:active {
  background-color: #fcc5df;
}

*::-webkit-scrollbar-thumb {
  border-radius: 5px;
  background-color: #cf3e6e;
  border: 2px double #ffffff;
}

*::-webkit-scrollbar-thumb:hover {
  background-color: #fc4985;
}

*::-webkit-scrollbar-thumb:active {
  background-color: #fc4985;
}

.cursor-pointer {
  cursor: pointer;
}
/*scroll bar ends*/
</style>
