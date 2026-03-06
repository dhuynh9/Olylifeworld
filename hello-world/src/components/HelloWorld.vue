<template>
  <div>
    <!-- Navbar -->
    <nav :class="['navbar', { 'scrolled': isScrolled }]">
      <div class="navbar-logo-container">
        <img src="@/assets/logo.png" alt="Logo" class="navbar-logo" />
      </div>
      <ul class="navbar-menu">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Shop</a></li>
        <li><a href="#">PEMF</a></li>
        <li><a href="#">Terahertz Waves</a></li>
        <li><a href="#">Geomagnetism</a></li>
        <li><a href="#">Usage Help</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>

    <!-- Hero Section -->
    <section class="hero-curve">
      <div class="hero-curve-inner">
        <img
          src="@/assets/frontpage.jpg"
          alt="Wellness Photo"
          class="hero-image"
          :style="{ transform: `scale(${1 + scrollOffset / 1000})` }"
        />
        <div class="hero-overlay"></div>
        <h1 class="hero-title">SUPPORTING TOTAL BODY WELLNESS</h1>

        <!-- Floating Circles -->
        <div class="floating-circle circle1"></div>
        <div class="floating-circle circle2"></div>
        <div class="floating-circle circle3"></div>
      </div>

      <!-- Wave SVG at bottom -->
      <svg class="hero-wave" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 150">
        <path fill="#f9f9f9" fill-opacity="1" d="M0,32L1440,128L1440,150L0,150Z"></path>
      </svg>
    </section>

    <!-- Innovative Dual Technology Section -->
<section class="content-section">
  <div class="circle">✓</div>
  <div class="content-container">
    <div class="content-image">
      <img src="@/assets/innovative.jpg" alt="Tera-P90 Device" />
    </div>
    <div class="content-text">
      <h2>Innovative Dual Technology</h2>
      <p>
        The OlyLife Tera-P90 stands out as a pioneering health technology that seamlessly integrates Terahertz Frequency and Pulsed Electro-Magnetic Field (PEMF) therapy, offering a multifaceted approach to wellness. Unlike conventional devices that specialize in one form of therapy, the Tera-P90 harmonizes the benefits of both Terahertz and PEMF waves, making it a uniquely versatile tool in the pursuit of health and vitality.
      </p>
      <p>
        Terahertz Frequency technology allows the Tera-P90 to resonate with the natural frequencies of the human body, promoting cellular health, improving blood circulation, and enhancing overall energy levels. Terahertz waves are known for their deep-penetrating ability, which can reach the subcutaneous tissues, offering therapeutic benefits that are both profound and long-lasting.
      </p>
      <p>
        Pulsed Electro-Magnetic Field (PEMF) therapy is renowned for its ability to stimulate cellular repair and regeneration. By emitting pulsating magnetic fields, the Tera-P90 aids in reducing inflammation, alleviating pain, and accelerating the healing process of bones and tissues. PEMF therapy has been extensively researched and validated for its effectiveness in improving various health conditions, from chronic pain to fractures and neurological disorders.
      </p>
      <p>
        The synergy of Terahertz Frequency and PEMF in the Tera-P90 means users can experience the combined advantages of both therapies.
      </p>

      <!-- Centered Buttons -->
      <div class="section-buttons">
        <button class="btn shop-btn">Shop</button>
        <button class="btn learn-btn">Learn More</button>
      </div>
    </div>
  </div>
</section>


    <!-- Wellness Background Section -->
    <section class="wellness-section">
      <div class="wellness-overlay">
        <h2 class="wellness-title">Wellness Technology Inspired by Nature</h2>
      </div>
    </section>

    <!-- PEMF Benefits Section -->
    <section class="content-section">
      <div class="circle">✓</div>
      <div class="content-container reverse-layout">
        <div class="content-text">
          <h2>Benefits of PEMF + Terahertz Therapy</h2>
          <p>The Potential Benefits Are:</p>
          <ul class="benefits-list">
            <li>Improved Sleep</li>
            <li>Pain Management</li>
            <li>Improved Mood</li>
            <li>Wound Healing</li>
            <li>Bone Health</li>
            <li>Immune Support</li>
            <li>Muscle Relaxation</li>
            <li>Improved Cognitive Function</li>
            <li>Reduced Inflammation</li>
          </ul>
        </div>
        <div class="content-image">
          <img src="@/assets/globe.jpg" alt="PEMF Device" />
        </div>
      </div>
    </section>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      isScrolled: false,
      scrollOffset: 0,
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 50;
      this.scrollOffset = window.scrollY;
    },
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=M+PLUS+Rounded+1c:wght@500;700&display=swap');

/* Navbar */
.navbar { display: flex; align-items: center; justify-content: space-between; padding: 10px 30px; background-color: rgba(255,255,255,0.8); font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; position: sticky; top:0; z-index:1000; transition: all 0.3s ease; backdrop-filter: blur(5px);}
.navbar.scrolled { background-color: #fff; box-shadow: 0 4px 6px rgba(0,0,0,0.1);}
.navbar-logo-container { background-color: transparent; padding: 2px 4px; border-radius: 4px; transition: all 0.3s ease;}
.navbar-logo { height:60px; width:120px; transition: all 0.3s ease;}
.navbar-menu { list-style:none; display:flex; margin:0; padding:0;}
.navbar-menu li { margin-left: 20px;}
.navbar-menu a { text-decoration:none; font-weight:600; font-size:16px; padding:5px 0; color:#2c3e50; position:relative; transition: color 0.3s, transform 0.2s;}
.navbar-menu a::after { content:''; position:absolute; width:0; height:2px; bottom:0; left:0; background-color:#42b983; transition: width 0.3s;}
.navbar-menu a:hover { transform:translateY(-2px);}
.navbar-menu a:hover::after { width:100%;}

/* Hero Section */
.hero-curve { position: relative; width:100%; overflow:hidden; }
.hero-curve-inner { position: relative; width:100%; clip-path: ellipse(100% 85% at 50% 10%); transition: transform 0.3s ease; }
.hero-image { width:100%; height:600px; object-fit:cover; display:block; transition: transform 0.3s ease; }
.hero-overlay { position:absolute; top:0; left:0; width:100%; height:100%; background: linear-gradient(180deg, rgba(0,0,0,0.3)0%, rgba(0,0,0,0)60%); z-index:1; }
.hero-title { position:absolute; top:50%; left:50%; transform:translate(-50%, -50%); font-size:3rem; font-family:'M PLUS Rounded 1c', sans-serif; font-weight:700; color:#fff; text-shadow:2px 2px 12px rgba(0,0,0,0.6); z-index:2; text-align:center; animation: fadeInDown 1s ease forwards; opacity:0; }
@keyframes fadeInDown { from { transform:translate(-50%, -60%); opacity:0; } to { transform:translate(-50%, -50%); opacity:1; } }

/* Floating Circles */
.floating-circle { position:absolute; border-radius:50%; background-color: rgba(66,185,131,0.4); animation: float 6s ease-in-out infinite alternate; z-index:2; }
.circle1 { width:80px; height:80px; top:20%; left:10%; }
.circle2 { width:120px; height:120px; top:40%; right:15%; }
.circle3 { width:60px; height:60px; top:65%; left:25%; }
@keyframes float { 0% { transform: translateY(0px);} 100% { transform: translateY(-20px);} }

/* Wave */
.hero-wave { display:block; width:100%; margin-top:-4px; }

/* Content Section */
.content-section { position:relative; padding:80px 20px; background-color:#f9f9f9; }
.circle { width:60px; height:60px; background-color:#42b983; border-radius:50%; display:flex; justify-content:center; align-items:center; color:white; font-weight:bold; font-size:24px; margin:0 auto 40px auto; }
.content-container { display:flex; align-items:center; justify-content:center; gap:40px; max-width:1200px; margin:0 auto; flex-wrap:wrap; }
.content-container.reverse-layout { flex-direction: row-reverse; }
.content-image img { width:400px; max-width:100%; border-radius:50% / 35%; border:6px solid #42b983; padding:5px; box-shadow:0 8px 20px rgba(66,185,131,0.3); transition: transform 0.3s ease, box-shadow 0.3s ease; }
.content-image img:hover { transform: scale(1.05); box-shadow:0 12px 28px rgba(66,185,131,0.4);}
.content-text { max-width:600px; }
.content-text h2 { font-size:2rem; margin-bottom:20px; color:#2c3e50; }
.content-text p { font-size:1.1rem; line-height:1.6; color:#555; }
.content-text ul.benefits-list { list-style-type: disc; padding-left:20px; }
.content-text ul.benefits-list li { margin-bottom:10px; }

/* Innovative Section Buttons */
.section-buttons {margin-top: 30px;display: flex;justify-content: center; /* center buttons */gap: 20px;flex-wrap: wrap;}

.btn {padding: 12px 30px;font-weight: 600;font-size: 16px;border-radius: 50px;cursor: pointer; border: none;transition: all 0.3s ease;box-shadow: 0 4px 8px rgba(66, 185, 131, 0.2); /* subtle shadow */}
.shop-btn {background-color: #42b983;color: white;}
.shop-btn:hover {background-color: #2e8b57;transform: scale(1.08);box-shadow: 0 8px 16px rgba(46, 139, 87, 0.4);}
.learn-btn {background-color: #66c399;color: white;}
.learn-btn:hover {background-color: #3fa072;transform: scale(1.08);box-shadow: 0 8px 16px rgba(63, 160, 114, 0.4);}
/* Wellness Section */
.wellness-section { position:relative; width:100%; height:500px; background-image:url('@/assets/wellness.jpg'); background-size:cover; background-position:center; display:flex; justify-content:center; align-items:center; overflow:hidden; }
.wellness-overlay { position:absolute; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.35); display:flex; justify-content:center; align-items:center; }
.wellness-title { font-family:'M PLUS Rounded 1c', sans-serif; font-size:3rem; color:#fff; text-align:center; text-shadow:2px 2px 12px rgba(0,0,0,0.6); padding:0 20px; }

/* Responsive */
@media (max-width:900px) { 
  .content-container { flex-direction: column; }
  .hero-title { font-size:2rem; }
  .wellness-title { font-size:2rem; }
  .section-buttons { flex-direction:column; align-items:center; }
}
</style>