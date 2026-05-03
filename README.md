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