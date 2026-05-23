# APSARA_RESTAURANT


    // Cart
      document.getElementById("cart-btn")?.addEventListener("click", showCart);
      document.getElementById("close-cart")?.addEventListener("click", hideCart);
      document.getElementById("cart-overlay")?.addEventListener("click", hideCart);

      // Smooth scroll
      document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
        anchor.addEventListener("click", function (e) {
          e.preventDefault();
          const target = document.querySelector(this.getAttribute("href"));
          if (target) target.scrollIntoView({ behavior: "smooth" });
        });
      });

      // Item review events
      document.getElementById("close-item-review")?.addEventListener("click", closeItemReview);
      document.getElementById("item-review-backdrop")?.addEventListener("click", closeItemReview);
      document.getElementById("item-review-submit")?.addEventListener("click", submitItemReview);

      document.querySelectorAll(".item-star-btn").forEach((star) => {
        star.addEventListener("mouseenter", () => updateItemStars(parseInt(star.dataset.v)));
        star.addEventListener("mouseleave", () => updateItemStars(itemSelectedRating));
        star.addEventListener("click", () => {
          itemSelectedRating = parseInt(star.dataset.v);
          updateItemStars(itemSelectedRating);
        });
      });

      document.getElementById("item-review-comment")?.addEventListener("keydown", (e) => {
        if (e.key === "Enter") submitItemReview();
      });






  <section id="feedback" class="py-16 bg-coffee-100 dark:bg-gray-800">
      <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-10">
          <h2
            class="text-3xl font-bold text-coffee-800 dark:text-coffee-200 mb-2"
          >
            មតិយោបល់របស់អ្នក
          </h2>
          <p class="text-coffee-500 dark:text-coffee-400 text-sm">
            យើងពេញចិត្តស្តាប់មតិពីអ្នក ដើម្បីកែលម្អសេវាកម្ម
          </p>
          <div class="flex items-center justify-center gap-3 mt-4">
            <div class="h-px w-16 bg-coffee-300 dark:bg-coffee-600"></div>
            <i class="fas fa-star text-litter-700 text-sm"></i>
            <div class="h-px w-16 bg-coffee-300 dark:bg-coffee-600"></div>
          </div>
        </div>

        <div class="bg-white dark:bg-gray-900 rounded-2xl shadow-lg p-8">
          <!-- Service star rating -->
          <div class="mb-6">
            <label
              class="block text-sm font-semibold text-coffee-700 dark:text-coffee-300 mb-3"
            >
              វាយតម្លៃសេវាកម្ម
            </label>
            <div id="star-rating" class="flex gap-2">
              <i
                class="star-btn fas fa-star text-2xl text-coffee-200 dark:text-gray-600 cursor-pointer transition-colors duration-150"
                data-value="1"
              ></i>
              <i
                class="star-btn fas fa-star text-2xl text-coffee-200 dark:text-gray-600 cursor-pointer transition-colors duration-150"
                data-value="2"
              ></i>
              <i
                class="star-btn fas fa-star text-2xl text-coffee-200 dark:text-gray-600 cursor-pointer transition-colors duration-150"
                data-value="3"
              ></i>
              <i
                class="star-btn fas fa-star text-2xl text-coffee-200 dark:text-gray-600 cursor-pointer transition-colors duration-150"
                data-value="4"
              ></i>
              <i
                class="star-btn fas fa-star text-2xl text-coffee-200 dark:text-gray-600 cursor-pointer transition-colors duration-150"
                data-value="5"
              ></i>
            </div>
            <p id="rating-label" class="text-xs text-coffee-400 mt-1">
              សូមចុចដើម្បីវាយតម្លៃ
            </p>
          </div>

          <!-- Name + Email -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-5">
            <div>
              <label
                class="block text-sm font-semibold text-coffee-700 dark:text-coffee-300 mb-1"
              >
                ឈ្មោះ <span class="text-red-400">*</span>
              </label>
              <input
                id="fb-name"
                type="text"
                placeholder="ឧ. សុខ ដារ៉ា"
                class="w-full border border-coffee-200 dark:border-gray-700 bg-coffee-50 dark:bg-gray-800 text-coffee-800 dark:text-white rounded-lg px-4 py-2.5 text-sm focus:outline-none focus:ring-2 focus:ring-coffee-400 placeholder-coffee-300 dark:placeholder-gray-500"
              />
            </div>
            <div>
              <label
                class="block text-sm font-semibold text-coffee-700 dark:text-coffee-300 mb-1"
              >
                អ៊ីម៉ែល
                <span class="text-coffee-400 font-normal">(ស្រេចចិត្ត)</span>
              </label>
              <input
                id="fb-email"
                type="email"
                placeholder="example@email.com"
                class="w-full border border-coffee-200 dark:border-gray-700 bg-coffee-50 dark:bg-gray-800 text-coffee-800 dark:text-white rounded-lg px-4 py-2.5 text-sm focus:outline-none focus:ring-2 focus:ring-coffee-400 placeholder-coffee-300 dark:placeholder-gray-500"
              />
            </div>
          </div>

          <!-- Category -->
          <!-- <div class="mb-5">
            <label
              class="block text-sm font-semibold text-coffee-700 dark:text-coffee-300 mb-1"
              >ប្រភេទមតិ</label
            >
            <select
              id="fb-category"
              class="w-full border border-coffee-200 dark:border-gray-700 bg-coffee-50 dark:bg-gray-800 text-coffee-800 dark:text-white rounded-lg px-4 py-2.5 text-sm focus:outline-none focus:ring-2 focus:ring-coffee-400"
            >
              <option value="">-- សូមជ្រើសរើស --</option>
              <option value="food">រសជាតិអាហារ</option>
              <option value="service">សេវាកម្ម</option>
              <option value="ambiance">បរិយាកាស</option>
              <option value="price">តម្លៃ</option>
              <option value="other">ផ្សេងទៀត</option>
            </select>
          </div> -->

          <!-- Message -->
          <div class="mb-6">
            <label
              class="block text-sm font-semibold text-coffee-700 dark:text-coffee-300 mb-1"
            >
              មតិយោបល់ <span class="text-red-400">*</span>
            </label>
            <textarea
              id="fb-message"
              rows="4"
              placeholder="សូមចែករំលែករបបគំនិតរបស់អ្នក..."
              class="w-full border border-coffee-200 dark:border-gray-700 bg-coffee-50 dark:bg-gray-800 text-coffee-800 dark:text-white rounded-lg px-4 py-2.5 text-sm focus:outline-none focus:ring-2 focus:ring-coffee-400 placeholder-coffee-300 dark:placeholder-gray-500 resize-none"
            ></textarea>
          </div>

          <button
            id="fb-submit"
            class="w-full bg-coffee-700 hover:bg-coffee-800 active:scale-95 text-white font-semibold py-3 rounded-xl transition-all duration-200 flex items-center justify-center gap-2"
          >
            <i class="fas fa-paper-plane text-sm"></i> បញ្ជូនមតិ
          </button>

          <!-- Success -->
          <div
            id="fb-success"
            class="hidden mt-5 bg-green-50 dark:bg-green-900/30 border border-green-300 dark:border-green-700 text-green-700 dark:text-green-400 rounded-xl px-5 py-4 flex items-center gap-3 text-sm"
          >
            <i class="fas fa-check-circle text-xl flex-shrink-0"></i>
            <div>
              <p class="font-semibold">អរគុណសម្រាប់មតិរបស់អ្នក!</p>
              <p class="text-xs mt-0.5 opacity-80">
                យើងនឹងពិចារណាលើការណែនាំរបស់អ្នក
              </p>
            </div>
          </div>

          <!-- Error -->
          <div
            id="fb-error"
            class="hidden mt-5 bg-red-50 dark:bg-red-900/30 border border-red-300 dark:border-red-700 text-red-600 dark:text-red-400 rounded-xl px-5 py-4 flex items-center gap-3 text-sm"
          >
            <i class="fas fa-exclamation-circle text-xl flex-shrink-0"></i>
            <p>សូមបំពេញឈ្មោះ និងមតិយោបល់</p>
          </div>
        </div>
      </div>
    </section>




    rrr
    <!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Register for Apsara Restaurant</title>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"
    />
    <script src="https://cdn.tailwindcss.com"></script>
    <script
      src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"
      defer
    ></script>
    <style>
      @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap");
      body {
        font-family: "Poppins", sans-serif;
      }
    </style>
  </head>
  <body
    class="bg-cover bg-center bg-no-repeat bg-fixed bg-blend-overlay bg-black/40 min-h-screen flex flex-col items-center py-10 px-4"
    style="
      background-image: url(https://i.pinimg.com/1200x/88/c6/9b/88c69b5a9cd258a0865ba01df5d38b54.jpg);
    "
  >
    <div class="container mx-auto px-4" x-data="{ tab: 'signup' }">
      <div
        class="max-w-4xl w-full m-auto bg-amber-50 rounded-3xl shadow-lg p-8 md:p-12"
      >
        <div
          class="w-full h-64 md:h-80 rounded-3xl overflow-hidden mb-12 relative"
        >
          <div
            id="slider"
            class="flex w-full h-full transition-transform duration-700 ease-in-out"
          >
            <img
              src="./picture/apsara-sign-in/Apsara.jpg"
              class="w-full h-full object-cover flex-shrink-0"
              alt="Slide 1"
            />
            <img
              src="./picture/apsara-sign-in/image-chef1.jpg"
              class="w-full h-full object-cover flex-shrink-0"
              alt="Slide 2"
            />
            <img
              src="./picture/apsara-sign-in/image-chef2.jpg"
              class="w-full h-full object-cover flex-shrink-0"
              alt="Slide 3"
            />
            <img
              src="./picture/apsara-sign-in/image-chef3.jpg"
              class="w-full h-full object-cover flex-shrink-0"
              alt="Slide 4"
            />
          </div>
          <div
            class="absolute inset-0 flex flex-col justify-center p-8 text-white pointer-events-none"
          >
            <h2 class="text-4xl underline font-bold italic font-serif">
              Apsara Restaurant
            </h2>
            <p class="text-gray-300">
              Register with us to receive priority reservations, <br />
              exclusive invitations to tasting events.
            </p>
          </div>
        </div>
        <h2 class="text-2xl font-bold text-gray-800 text-center">
          Welcome To Our Restaurant
        </h2>
        <p class="text-gray-500 text-center mt-2">
          Sign up if you don't have an account but if you have account please
          Sign in
        </p>
        <div class="md:flex-row gap-12 items-start">
          <div class="p-8">
            <div class="flex justify-center mb-6">
              <button
                @click="tab = 'signup'"
                :class="{ 'bg-blue-500 text-white': tab === 'signup', 'bg-gray-200 text-gray-700': tab !== 'signup' }"
                class="px-4 py-2 rounded-l-md focus:outline-none transition-colors duration-300"
              >
                Sign Up
              </button>
              <button
                @click="tab = 'login'"
                :class="{ 'bg-blue-500 text-white': tab === 'login', 'bg-gray-200 text-gray-700': tab !== 'login' }"
                class="px-4 py-2 rounded-r-md focus:outline-none transition-colors duration-300"
              >
                Sign in
              </button>
            </div>
            <form x-show="tab === 'signup'" class="space-y-4">
              <div class="relative">
                <label for="name" class="block text-gray-800 font-bold"
                  >Full Name:</label
                >
                <input
                  type="text"
                  class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500 pl-10"
                  placeholder="Full Name"
                />
                <i class="fas fa-user absolute left-3 top-9 text-gray-400"></i>
              </div>
              <div class="relative">
                <label for="email" class="block text-gray-800 font-bold"
                  >Email:</label
                >
                <input
                  type="email"
                  placeholder="Email"
                  required
                  class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500 pl-10"
                />
                <i
                  class="fas fa-envelope absolute left-3 top-9 text-gray-400"
                ></i>
              </div>
              <div class="relative">
                <label for="password" class="block text-gray-800 font-bold"
                  >Password:</label
                >
                <input
                  type="password"
                  placeholder="Password"
                  required
                  class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500 pl-10"
                />
                <i class="fas fa-lock absolute left-3 top-9 text-gray-400"></i>
              </div>
              <!-- Sign Up Form -->
              <button
                class="w-full bg-gradient-to-r from-blue-500 to-purple-600 text-white py-2 rounded-md hover:opacity-90 transition-opacity duration-300 transform hover:scale-105"
              >
                Sign Up
              </button>
            </form>
            <form x-show="tab === 'login'" class="space-y-4">
              <div class="relative">
                <label for="email" class="block text-gray-800 font-bold"
                  >Email:</label
                >
                <input
                  type="email"
                  placeholder="Email"
                  required
                  class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500 pl-10"
                />
                <i
                  class="fas fa-envelope absolute left-3 top-9 text-gray-400"
                ></i>
              </div>
              <div class="relative">
                <label for="password" class="block text-gray-800 font-bold"
                  >Password:</label
                >
                <input
                  type="password"
                  placeholder="Password"
                  required
                  class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500 pl-10"
                />
                <i class="fas fa-lock absolute left-3 top-9 text-gray-400"></i>
                <a
                  href="#"
                  class="text-sm font-thin text-gray-800 hover:underline mt-2 inline-block hover:text-indigo-600"
                  >Forget Password</a
                >
              </div>
              <!-- Sign In Form -->
              <button
                class="w-full bg-gradient-to-r from-blue-500 to-purple-600 text-white py-2 rounded-md hover:opacity-90 transition-opacity duration-300 transform hover:scale-105"
              >
                Sign in
              </button>
            </form>
            <div
              id="third-party-auth"
              class="flex items-center justify-center mt-5 flex-wrap"
            >
              <button
                href="#"
                class="hover:scale-105 ease-in-out duration-300 shadow-lg p-2 rounded-lg m-1"
              >
                <img
                  class="max-w-[25px]"
                  src="https://ucarecdn.com/8f25a2ba-bdcf-4ff1-b596-088f330416ef/"
                  alt="Google"
                />
              </button>
              <button
                href="#"
                class="hover:scale-105 ease-in-out duration-300 shadow-lg p-2 rounded-lg m-1"
              >
                <img
                  class="max-w-[25px] filter dark:invert"
                  src="https://ucarecdn.com/be5b0ffd-85e8-4639-83a6-5162dfa15a16/"
                  alt="Github"
                />
              </button>

              <button
                href="#"
                class="hover:scale-105 ease-in-out duration-300 shadow-lg p-2 rounded-lg m-1"
              >
                <img
                  class="max-w-[25px]"
                  src="https://ucarecdn.com/6f56c0f1-c9c0-4d72-b44d-51a79ff38ea9/"
                  alt="Facebook"
                />
              </button>
            </div>
            <div
              class="text-gray-500 flex text-center flex-col mt-4 items-center text-sm"
            >
              <p class="cursor-default">
                By signing in, you agree to our
                <a
                  class="group text-blue-400 transition-all duration-100 ease-in-out"
                  href="#"
                >
                  <span
                    class="cursor-pointer bg-left-bottom bg-gradient-to-r from-blue-400 to-blue-400 bg-[length:0%_2px] bg-no-repeat group-hover:bg-[length:100%_2px] transition-all duration-500 ease-out"
                  >
                    Terms
                  </span>
                </a>
                and
                <a
                  class="group text-blue-400 transition-all duration-100 ease-in-out"
                  href="#"
                >
                  <span
                    class="cursor-pointer bg-left-bottom bg-gradient-to-r from-blue-400 to-blue-400 bg-[length:0%_2px] bg-no-repeat group-hover:bg-[length:100%_2px] transition-all duration-500 ease-out"
                  >
                    Privacy Policy
                  </span>
                </a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
  <script>
    const slider = document.getElementById("slider");
    const slides = slider.children;
    let currentIndex = 0;

    function nextSlide() {
      currentIndex++;

      // If we reach the end, reset to the first slide
      if (currentIndex >= slides.length) {
        currentIndex = 0;
      }

      // Move the slider left/right
      // -100% * index shifts the view to the next image
      slider.style.transform = `translateX(-${currentIndex * 100}%)`;
    }

    // Change image every 4 seconds
    setInterval(nextSlide, 4000);
  </script>
</html>
