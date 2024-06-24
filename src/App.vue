<template>
  <div class="container">
    <header>
      <h1>{{ pageTitle }}</h1>
    </header>
    <main>
      <section class="hero">
        <h2>Welcome to Our Website!</h2>
        <p>Explore the amazing features we offer.</p>
        <button @click="toggleModal">Learn More</button>
      </section>
      <section class="features">
        <div class="feature">
          <img src="./assets/feature1.jpeg" alt="Feature 1">
          <h3>Feature 1</h3>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        <div class="feature">
          <img src="./assets/feature2.jpeg" alt="Feature 2">
          <h3>Feature 2</h3>
          <p>Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
        </div>
        <div class="feature">
          <img src="./assets/feature3.jpeg" alt="Feature 3">
          <h3>Feature 3</h3>
          <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
        </div>
      </section>
      <section class="testimonial">
        <blockquote>
          <p>"This website is amazing! It has everything I need and more."</p>
          <footer>- Happy Customer</footer>
        </blockquote>
      </section>
    </main>
    <footer>
      <p>&copy; 2024 Our Website. Zakia Aulia Putra.</p>
    </footer>
    <div class="modal" v-if="showModal">
      <div class="modal-content">
        <span class="close" @click="toggleModal">&times;</span>
        <h2>About Us</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pageTitle: "Welcome to Our Website!",
      showModal: false,
      isHighlighted: false,
      inputText: "",
      boxColor: "lightblue",
      boxContent: "Hover me to change color!",
      listItems: ["Item 1", "Item 2", "Item 3"]
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    updateText(event) {
      this.inputText = event.target.value;
    },
    toggleHighlight() {
      this.isHighlighted = !this.isHighlighted;
    },
    changeColor() {
      const colors = ["lightblue", "lightgreen", "lightcoral", "lightsalmon"];
      const randomIndex = Math.floor(Math.random() * colors.length);
      this.boxColor = colors[randomIndex];
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

header {
  background-color: #333;
  color: white;
  padding: 20px;
  text-align: center;
}

main {
  padding: 20px;
}

.hero {
  text-align: center;
  margin-bottom: 40px;
}

.hero h2 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.hero p {
  font-size: 1.2rem;
  margin-bottom: 30px;
}

.hero button {
  padding: 10px 20px;
  font-size: 1.2rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.features {
  display: flex;
  justify-content: space-around;
  margin-bottom: 40px;
}

.feature {
  text-align: center;
}

.feature img {
  max-width: 200px;
}

.feature h3 {
  margin-top: 20px;
  font-size: 1.5rem;
}

.testimonial {
  text-align: center;
  margin-bottom: 40px;
}

.testimonial blockquote {
  font-size: 1.5rem;
}

.testimonial footer {
  margin-top: 10px;
  font-style: italic;
}

footer {
  background-color: #333;
  color: white;
  padding: 20px;
  text-align: center;
}

.modal {
  display: none;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  background-color: #fefefe;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
</style>
