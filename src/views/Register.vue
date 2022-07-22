<template>
  <section class="contact-background" id="contact">
    <div class="container">
      <div class="formm justify-content-center">
        <div class="row">
          <div class="form-cont col-md-6 col-sm-12 col- col-lg-5 col-12">
            <form
              @submit.prevent="registerUser"
              class="contactMe card-shadow slider container"
            >
              <div class="form-text text-center"></div>
              <label for="">NAME:</label>
              <input
                class="form-input neu-border-inset"
                type="text"
                v-model="name"
                required
                placeholder="Enter your surname*"
              />
              <label for="">SURNAME:</label>
              <input
                type="text"
                class="form-input email neu-border-inset"
                v-model="surname"
                required
                placeholder="Enter your surname*"
              />
              <label for="">EMAIL:</label>
              <input
                class="form-input neu-border-inset subject"
                type="email"
                v-model="email"
                placeholder="Enter your email*"
                required
              />
              <div class="submit mb-3">
                <button type="Submit" class="mb-3 button-body">REGISTER</button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
  
  <script>
export default {
  data() {
    return {
      name: "",
      surname: "",
      email: "",
    };
  },
  methods: {
    registerUser() {
      fetch("https://dlonra-academy.herokuapp.com/register", {
        method: "POST",
        body: JSON.stringify({
          name: this.name,
          surname: this.surname,
          email: this.email,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })  
        .then((response) => response.json())
        .then((result, err) => {
          if(err){console.log(err)
          }
          else{
            alert(result);
          }
        })
        .catch(err => console.log(err));
    },
  },
};
</script>
  
  <style scoped>
.form-cont {
  display: flex;
  align-items: center;
}
.image-div {
  display: flex;
  align-items: flex-end;
  min-height: 100vh !important;
}
img {
  width: 100% !important;
  object-fit: fill !important;
  height: 90% !important;
}

.icons {
  font-size: 30px;
  color: rgba(115, 179, 106, 0.966) !important;
}
h5 {
  font-weight: bold;
}
.green {
  color: rgba(115, 179, 106, 0.966);
}
h6 {
  color: rgba(115, 179, 106, 0.966);
  font-weight: bold;
}
.iframe {
  margin-top: 150px;
}
form {
  max-width: 100%;
  margin: 30px auto;
  text-align: left;
  border-radius: 10px;
}
label {
  color: rgb(0, 0, 0);
  display: inline-block;
  margin: 1px 0 2px;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input {
  display: block;
  padding: 5px 3px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  color: rgb(0, 0, 0);
  background-color: rgba(255, 202, 29, 0.966);
  outline: none !important;
}

.button-body {
  background: rgba(255, 202, 29, 0.966);
  border: 0;
  padding: 7px 15px;
  margin-top: 30px;
  color: rgb(0, 0, 0);
  cursor: pointer;
  margin-bottom: 10px !important;
  font-weight: bold;
  letter-spacing: 1px;
}
button:hover {
  opacity: 0.8;
  background: #12613b;
  color: rgb(255, 255, 255) !important;
}
.span2 {
  display: block;
}
.span {
  display: none !important;
}
.error {
  color: #ff0062;
  margin-top: 10px;
  font-size: 0.8em;
  font-weight: bold;
}
.contactMe {
  width: 100%;
  margin: 0px;
  padding: 0;
}
.contact-icons {
  font-size: 20px !important;
}
.formm {
  width: 100%;
}
.row {
  min-height: 100vh;
}

.slide {
  animation-duration: 1s;
  animation-name: slidein;
}
template {
  background-color: #f2f2fc;
}

@keyframes slidein {
}

@media all and (max-width: 800px) {
}
@media all and (max-width: 768px) {
  .image-div {
    display: none !important;
  }
}
</style> 
