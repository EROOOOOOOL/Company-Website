<template>
    <div>
      <header>
        <img src="../assets/logo.png" alt="Company Logo" class="logo" />
        <nav>
          <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#contact">Contact Us</a></li>
          </ul>
        </nav>
      </header>
  
      <section id="home">
        <div class="banner">
          <h2>Welcome to Pixel Studio – Where Innovation Meets Creativity!</h2>
          <p>We craft cutting-edge websites, mobile apps, and tailored solutions to bring your ideas to life. Let's build something extraordinary together!</p>
        </div>
      </section>
  
      <section id="services">
        <h2>Our Services</h2>
        <div class="service-list">
          <div class="service">
            <h3>Web Development</h3>
            <p>At Pixel Studio, we create stunning, responsive, and user-friendly websites that bring your vision to life. 
              Our expert developers combine creativity with the latest technologies to deliver high-performing websites 
              that not only look great but function flawlessly. Whether you need a sleek portfolio, a robust e-commerce platform, 
              or a custom web application, Pixel Studios ensures your online presence stands out and engages your audience.</p>
          </div>
          <div class="service">
            <h3>Mobile Development</h3>
            <p>Pixel Studio specializes in crafting innovative and intuitive mobile applications for both iOS and Android platforms. 
              Our team blends functionality and aesthetics to create apps that provide seamless user experiences and solve real-world problems. 
              From concept to deployment, we ensure every app is tailored to your business needs and optimized for performance, scalability, and user satisfaction.</p>
          </div>
          <div class="service">
            <h3>Project Management</h3>
            <p>At Pixel Studio, we believe successful projects are built on strong planning and communication. 
              Our project management team ensures every aspect of your project is handled with precision and care. 
              From initial brainstorming to final delivery, we keep your goals at the forefront, maintaining transparency, meeting deadlines, 
              and ensuring high-quality results. With our collaborative approach, your vision is always the priority.</p>
          </div>
        </div>
      </section>
  
      <section id="contact">
        <h2>Contact Us</h2>
        <p>If you have any questions, feel free to reach out to us using the form below!</p>
        <form @submit.prevent="submitForm" class="contact-form">
          <div class="form-group">
            <label for="name">Your Name</label>
            <input
              type="text"
              id="name"
              placeholder="Enter your name"
              v-model="name"
              required
            />
          </div>
          <div class="form-group">
            <label for="email">Your Email</label>
            <input
              type="email"
              id="email"
              placeholder="Enter your email"
              v-model="email"
              required
            />
          </div>
          <div class="form-group">
            <label for="message">Your Message</label>
            <textarea
              id="message"
              placeholder="Type your message here..."
              v-model="message"
              required
            ></textarea>
          </div>
          <button type="submit" class="submit-btn">Send Message</button>
        </form>
      </section>

      <div v-if="showPopup" class="popup">
      <div class="popup-content">
        <span class="close-btn" @click="closePopup">&times;</span>
        <p>Thank you, {{ name }}. Your message has been sent!</p>
      </div>
      </div>

      <footer>
        <div class="social-links">
          <a href="https://www.google.com/search?client=opera-gx&q=facebook&sourceid=opera&ie=UTF-8&oe=UTF-8">Facebook</a>
          <a href="https://www.google.com/search?client=opera-gx&q=instagram&sourceid=opera&ie=UTF-8&oe=UTF-8">Instagram</a>
          <a href="https://www.google.com/search?client=opera-gx&q=linkedin&sourceid=opera&ie=UTF-8&oe=UTF-8">LinkedIn</a>
        </div>
        <p>&copy; 2025 All Rights Reserved.</p>
      </footer>
    </div>
  </template>

<style>
.banner {
  position: relative;
  text-align: center;
  padding: 10rem 2rem;
  background-image: url('../assets/banner.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  color: white;
}

.banner h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: white;
}

.banner p {
  font-size: 1.25rem;
  margin-top: 0;
  color: white;
}

.popup {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup-content {
  background: white;
  padding: 20px;
  border-radius: 8px;
  text-align: center;
  position: relative;
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 18px;
  cursor: pointer;
}
</style>

  
<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      message: '',
      showPopup: false
    };
  },
  methods: {
    submitForm() {
      this.showPopup = true;
    },
    closePopup() {
      this.showPopup = false;
    }
  }
};
</script>
  