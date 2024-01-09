<template>
  <div class="home flex-grow-1 d-flex flex-column align-items-center justify-content-center">
    

    <main id="main">
      <section id="hero" class="border-bottom border-black">
        <div class="container-fluid">
          <div class="row">
            <div class="col-4 mt-5 d-flex fs-1">
              <!-- <p class="fw-bolder heroText">Let Food Be Thy Medicine</p> -->
            </div>
          </div>
        </div>
      </section>
        <!-- ======= About Section ======= -->
        <section id="about" class="about">
          <div class="container-fluid">
            <div class="row">
              <div
                class="col-lg-5 text-center animate__animated animate__rollIn"
                
              >
                <img src="../assets/img/secondaryLogoPurple.png" alt="Secondary Logo" class="w-50">
              </div>

              <div
                class="col-lg-7 d-flex flex-column justify-content-center align-items-stretch"
              >
                <div class="content">
                  <h3 class="text-dark text-center">
                    Why Choose
                    <strong>Bowl of Heaven?</strong>
                  </h3>
                  <p class="playFair fs-5 text-dark">
                    Bowl of Heaven has spent years perfecting the Best All-Natural Treat! Made of 100% whole food, this meal replacement is packed with delicious healthy super fruits like acai, strawberries, bananas, blueberries and more. We infuse our exclusive super-charged high antioxident blend in every bowl and smoothie, for added rejuvenation for your body and soul. Boost your energy without any added refined sugars, preservatives, gluten or dairy.
                  </p>
                  <p class="playFair fs-5 text-dark">Our Bowls and Smoothies are made fresh just for you, topped with an organic granola, fruit, and drizzled with honey to delight your senses completely. Are you a creative genius? We love to create special blends for each individual utilizing delicious and nutritious add-ins that can be added to your favorite bowl or smoothie. Visit us today…and let food be thy medicine.

                  </p>
                </div>
              </div>
            </div>
          </div>
        </section>
        <!-- End About Section -->
        

        <!-- ======= Seasonal Section ======= -->
        <section id="seasonal" class="seasonal border-top border-bottom border-black pb-1">
          <div class="container">
            <div class="section-title">
              <h2 class="text-dark">Check Out Our Seasonal Flavors</h2>
            </div>

            <div class="row">
              <SeasonalSlide />

            </div>
          </div>
        </section>
        <!-- End Seasonal Section -->

        <!-- ======= Menu Section ======= -->
        <section id="ourStory" class="ourStory border-bottom border-black">
          <div class="container-fluid">
            <div class="section-title">
              <h2 class="text-dark">Our <span>Story</span></h2>
            </div>

            <div class="row">
              <div class="col-lg-12 d-flex justify-content-center">
                
              </div>
            </div>

            <div class="row ourStory-container">
              <div class="col-md-7 pt-4">
                <h2 class="ms-5 mb-4 text-dark"><i>Then...</i></h2>
                <p class="ps-4 fs-5 playFair">Shortly after learning of Brent's diagnosis with Parkinson's disease, Gigi & Brent both knew it was time to make some life changes. Both experienced business people, they took that knowledge and combined it with what they had learned about longevity and living a fuller life. They had realized a very important factor; what you eat really does matter. They went after the facts, and turned to nutrition with scientific evidence to built a menu that would in turn serve the community they loved. Bowl of Heaven offers a plant-based approach with fresh fruits and vegetables, berries with antioxidant properties. In 2010, Bowl of Heaven was born. Together, they established the very first OG acai bowls in the treasure valley; pioneering recipes that have been tried and true, paid with their own blood, sweat and tears. Today, Brent is a walking miracle. He has been diagnosed with Parkinsons for over 25 years, and continues to move with a smile on his face. Gigi and Brent are now enjoying as much time as they possibly can together.</p>
              </div>
              <div class="col-md-5">
                <img class="rounded" src="../assets/img/gigiBrent.jpeg" alt="Gigi and Brent">
              </div>
              <div class="col-md-4 ps-5 mt-5">
                <img class="rounded famPic" src="../assets/img/fernandezFam.jpg" alt="Fernandez Family">
              </div>
              <div class="col-md-7 pt-4 mt-5">
                <h2 class="ms-3 mb-4 text-dark"><i>Now...</i></h2>
                <p class="fs-5 pe-4 playFair">The Legacy Continues: Gigi and Brent decided to step away from the day-to-day life that Bowl of Heaven offers, and sold it to Gigi's nephew and his wife, Christopher & Felicia Fernandez. Both as loving and caring, with a deep desire to encompass nutrition and serve the community they grew up in. Together, they have five children and find every day a new adventure.</p>
              </div>
            </div>
          </div>
        </section>
        <!-- End Menu Section -->


        <!-- ======= Contact Section ======= -->
        <section id="contact" class="contact">
          <div class="container">
            <div class="section-title">
              <h2 class="text-dark"><span>Contact</span> Us</h2>
              <h6 class="mt-2">
                We'd love to hear from you! Give us a call or come see us!
              </h6>
            </div>
          </div>

          <div class="map">
            <iframe
              style="border: 0; width: 100%; height: 450px"
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2884.907511072958!2d-116.3581570836447!3d43.691686170029335!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x54afaab71548471b%3A0xf798f7f926203e9!2s435%20S%20Eagle%20Rd%2C%20Eagle%2C%20ID%2083616!5e0!3m2!1sen!2sus!4v1698760108993!5m2!1sen!2sus"
              frameborder="0"
              allowfullscreen
            ></iframe>
          </div>

          <div class="container mt-5">
            <div class="info-wrap">
              <div class="row d-flex justify-content-evenly">
                <div class="col-lg-3 col-md-6 info ms-md-4">
                  <i class="fa fa-map"></i>
                  <h4>Location:</h4>
                  <p>435 S Eagle Rd, <br> Eagle, ID</p>
                </div>

                <div class="col-lg-3 col-md-6 info mt-4 mt-lg-0">
                  <i class="fa fa-clock"></i>
                  <h4>Open Hours:</h4>
                  <p>Monday-Saturday:<br />9:00 AM - 7:00 PM</p>
                </div>

                <!-- <div class="col-lg-3 col-md-6 info mt-4 mt-lg-0">
                  <i class="fa fa-envelope"></i>
                  <h4>Email:</h4>
                  <p>info@example.com<br />contact@example.com</p>
                </div> -->

                <div class="col-lg-3 col-md-6 info mt-4 mt-lg-0 ps-3">
                  <i class="fa fa-phone"></i>
                  <h4>Call:</h4>
                  <p>(208) 939-0748</p>
                </div>
              </div>
            </div>

            <!-- <form
            action="forms/contact.php"
            method="post"
            role="form"
            class="php-email-form"
          >
            <div class="row">
              <div class="col-md-6 form-group">
                <input
                  type="text"
                  name="name"
                  class="form-control"
                  id="name"
                  placeholder="Your Name"
                  required
                />
              </div>
              <div class="col-md-6 form-group mt-3 mt-md-0">
                <input
                  type="email"
                  class="form-control"
                  name="email"
                  id="email"
                  placeholder="Your Email"
                  required
                />
              </div>
            </div>
            <div class="form-group mt-3">
              <input
                type="text"
                class="form-control"
                name="subject"
                id="subject"
                placeholder="Subject"
                required
              />
            </div>
            <div class="form-group mt-3">
              <textarea
                class="form-control"
                name="message"
                rows="5"
                placeholder="Message"
                required
              ></textarea>
            </div>
            <div class="my-3">
              <div class="loading">Loading</div>
              <div class="error-message"></div>
              <div class="sent-message">
                Your message has been sent. Thank you!
              </div>
            </div>
            <div class="text-center">
              <button type="submit">Send Message</button>
            </div>
          </form> -->
          </div>
        </section>
        <!-- End Contact Section -->
      </main>
  </div>
</template>

<script>
export default {
  setup() {
    return {}
  }
}
</script>

<style scoped lang="scss">
#hero {
  background-image: url('../assets/img/pbPassionCreative.jpg');
  background-size: cover;
  background-position: center;
  min-height: 85vh;
  position: relative;
  margin-top: -6.7em;
}

.heroText {
  font-size: 120px;
}

.famPic {
  height: 600px;
}
</style>
