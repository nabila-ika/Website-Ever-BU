<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ever-BU: Dari Bumi, untuk Hidup Sehat Berkelanjutan!</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Custom font if needed, otherwise Tailwind's default is Inter */
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Basic scroll behavior for smooth transitions if using anchors */
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body class="min-h-screen bg-gradient-to-br from-green-50 to-yellow-50 text-gray-800">

    <!-- Notification Container -->
    <div id="notification-container"></div>

    <!-- Header -->
    <header class="bg-gradient-to-r from-green-600 to-yellow-600 text-white p-4 shadow-lg rounded-b-xl">
        <div class="container mx-auto flex justify-between items-center">
            <!-- Logo Ever-BU -->
            <div class="flex items-center space-x-2">
                <img src="logo brand.png" height="100px" width="50px"  alt="Ever-BU Logo" class="h-10 rounded-lg shadow-md" />
                <h1 class="text-3xl font-bold tracking-wider">Ever-BU</h1>
            </div>

            <!-- Navigation -->
            <nav>
                <ul class="flex space-x-6">
                    <li>
                        <button onclick="navigateTo('home')" id="nav-home" class="hover:text-yellow-200 transition-colors duration-300">
                            Beranda
                        </button>
                    </li>
                    <li>
                        <button onclick="navigateTo('products')" id="nav-products" class="hover:text-yellow-200 transition-colors duration-300">
                            Produk
                        </button>
                    </li>
                    <li>
                        <button onclick="navigateTo('contact')" id="nav-contact" class="hover:text-yellow-200 transition-colors duration-300">
                            Kontak
                        </button>
                    </li>
                    <li>
                        <button onclick="navigateTo('cart')" id="nav-cart" class="relative hover:text-yellow-200 transition-colors duration-300 flex items-center">
                            <!-- Shopping Cart Icon SVG -->
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-shopping-cart">
                                <circle cx="8" cy="21" r="1" />
                                <circle cx="19" cy="21" r="1" />
                                <path d="M2.05 2.05h2l2.66 12.42a2 2 0 0 0 2 1.58h9.78a2 2 0 0 0 1.95-1.57l1.65-7.43H5.12" />
                            </svg>
                            <span id="cart-item-count" class="absolute -top-2 -right-2 bg-red-500 text-white text-xs font-bold rounded-full h-5 w-5 flex items-center justify-center hidden">
                                0
                            </span>
                        </button>
                    </li>
                    <li>
                        <button onclick="handleAuthClick()" id="auth-button" class="bg-yellow-500 hover:bg-yellow-600 text-white px-4 py-2 rounded-full shadow-md transition-all duration-300 flex items-center space-x-2">
                            <!-- User Icon SVG -->
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-user">
                                <path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2" />
                                <circle cx="12" cy="7" r="4" />
                            </svg>
                            <span id="auth-text">Login</span>
                        </button>
                    </li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Main Content Area -->
    <main id="main-content" class="container mx-auto p-4 py-8 min-h-[calc(100vh-160px)]">
        <!-- Content will be loaded here by JavaScript -->
    </main>

    <!-- Footer -->
    <footer class="bg-gradient-to-r from-green-700 to-yellow-700 text-white p-6 text-center mt-8 rounded-t-xl">
        <div class="container mx-auto">
            <p class="text-lg mb-2">
                Ever-BU: From Earth, For a Healthy Sustainable Life!
            </p>
            <p class="text-sm">
                &copy; <span id="current-year"></span> Ever-BU. Semua Hak Dilindungi.
            </p>
            <div class="flex justify-center space-x-4 mt-4">
                <!-- Social Media Icons (example) -->
                <a href="#" class="hover:text-yellow-300 transition-colors duration-300">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-instagram">
                        <rect width="20" height="20" x="2" y="2" rx="5" ry="5" />
                        <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z" />
                        <line x1="17.5" x2="17.5" y1="6.5" y2="6.5" />
                    </svg>
                </a>
                <a href="#" class="hover:text-yellow-300 transition-colors duration-300">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-facebook">
                        <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z" />
                    </svg>
                </a>
                <a href="#" class="hover:text-yellow-300 transition-colors duration-300">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-twitter">
                        <path d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17-19 11.6 9.2-1 14.3-5 17-8.5C20.5 6 22 4 22 4Z" />
                    </svg>
                </a>
            </div>
        </div>
    </footer>

    <script>
        // Global state variables
        let currentPage = 'home';
        let cart = [];
        let isLoggedIn = false;
        let currentUser = null;
        let notificationTimeout;

        // Data produk Ever-BU
        const productsData = [
            {
                id: 1,
                name: 'PumpCrunch',
                description: 'Sereal labu kuning kaya serat, aman untuk penderita diabetes, dan bergizi tinggi. Harga yang tertera untuk 250 gram.',
                price: 45000,
                image: 'pumpcrunch kemasan.jpeg',
            },
            {
                id: 2,
                name: 'EcoGrow',
                description: 'Pupuk organik cair yang mudah diserap tanaman, meningkatkan kesuburan tanah, dan mengurangi ketergantungan pupuk kimia. Harga yang tertera untuk 500 ml.',
                price: 25000,
                image: 'ecogrow kemasan.jpeg',
            },
            {
                id: 3,
                name: 'SeedChew',
                description: 'Biji labu panggang aneka rasa, camilan sehat, lezat, tanpa pewarna dan pengawet buatan. Harga yang tetera untuk 50 gram.',
                price: 15000,
                image: 'seedchew kemasan.jpeg',  
            },
        ];

        // Utility function to format currency
        function formatCurrency(amount) {
            return `Rp${amount.toLocaleString('id-ID')}`;
        }

        // Function to show notifications
        function showNotification(message, type) {
            clearTimeout(notificationTimeout); // Clear any existing timeout
            const notificationContainer = document.getElementById('notification-container');
            let notificationDiv = document.getElementById('app-notification');

            if (!notificationDiv) {
                notificationDiv = document.createElement('div');
                notificationDiv.id = 'app-notification';
                notificationDiv.className = 'fixed bottom-4 right-4 p-4 rounded-lg shadow-lg text-white z-50 transition-opacity duration-300 opacity-0';
                notificationContainer.appendChild(notificationDiv);
            }

            notificationDiv.textContent = message;
            notificationDiv.className = `fixed bottom-4 right-4 p-4 rounded-lg shadow-lg text-white z-50 transition-opacity duration-300 opacity-100 ${type === 'success' ? 'bg-green-500' : type === 'error' ? 'bg-red-500' : 'bg-blue-500'}`;

            notificationTimeout = setTimeout(() => {
                notificationDiv.classList.remove('opacity-100');
                notificationDiv.classList.add('opacity-0');
                setTimeout(() => {
                    if (notificationDiv.parentNode) {
                        notificationDiv.parentNode.removeChild(notificationDiv);
                    }
                }, 300); // Remove after fade out
            }, 3000);
        }

        // Function to update cart item count in header
        function updateCartItemCount() {
            const count = cart.reduce((acc, item) => acc + item.quantity, 0);
            const cartCountSpan = document.getElementById('cart-item-count');
            if (cartCountSpan) {
                cartCountSpan.textContent = count;
                if (count > 0) {
                    cartCountSpan.classList.remove('hidden');
                } else {
                    cartCountSpan.classList.add('hidden');
                }
            }
        }

        // Function to add product to cart
        function addToCart(productId) {
            const product = productsData.find(p => p.id === productId);
            if (!product) return;

            const existingItem = cart.find(item => item.id === product.id);
            if (existingItem) {
                cart = cart.map(item =>
                    item.id === product.id ? { ...item, quantity: item.quantity + 1 } : item
                );
            } else {
                cart = [...cart, { ...product, quantity: 1 }];
            }
            showNotification(`${product.name} ditambahkan ke keranjang!`, 'success');
            updateCartItemCount();
            if (currentPage === 'cart') renderCartPage(); // Re-render cart if on cart page
        }

        // Function to update product quantity in cart
        function updateQuantity(productId, newQuantity) {
            if (newQuantity < 1) {
                removeFromCart(productId);
                return;
            }
            cart = cart.map(item =>
                item.id === productId ? { ...item, quantity: newQuantity } : item
            );
            updateCartItemCount();
            renderCartPage(); // Re-render cart to show updated quantities and total
        }

        // Function to remove product from cart
        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            showNotification('Produk dihapus dari keranjang.', 'info');
            updateCartItemCount();
            renderCartPage(); // Re-render cart
        }

        // Function to clear the cart
        function clearCart() {
            cart = [];
            showNotification('Keranjang dikosongkan.', 'info');
            updateCartItemCount();
            renderCartPage(); // Re-render cart
        }

        // Function to handle auth button click (login/logout)
        function handleAuthClick() {
            if (isLoggedIn) {
                isLoggedIn = false;
                currentUser = null;
                showNotification('Anda telah logout.', 'info');
                navigateTo('home');
            } else {
                navigateTo('login');
            }
            updateAuthButton();
        }

        // Function to update auth button text
        function updateAuthButton() {
            const authButton = document.getElementById('auth-button');
            const authText = document.getElementById('auth-text');
            if (authButton && authText) {
                if (isLoggedIn) {
                    authButton.classList.remove('bg-yellow-500', 'hover:bg-yellow-600');
                    authButton.classList.add('bg-red-500', 'hover:bg-red-600');
                    authText.textContent = 'Logout';
                } else {
                    authButton.classList.remove('bg-red-500', 'hover:bg-red-600');
                    authButton.classList.add('bg-yellow-500', 'hover:bg-yellow-600');
                    authText.textContent = 'Login';
                }
            }
        }

        // Function to set active navigation link style
        function updateNavStyles() {
            const navButtons = document.querySelectorAll('header nav button');
            navButtons.forEach(button => {
                button.classList.remove('text-yellow-200', 'font-semibold');
            });
            const activeNavButton = document.getElementById(`nav-${currentPage}`);
            if (activeNavButton) {
                activeNavButton.classList.add('text-yellow-200', 'font-semibold');
            }
        }

        // Page rendering functions
        const mainContentDiv = document.getElementById('main-content');

        function renderHomePage() {
            mainContentDiv.innerHTML = `
                <section class="text-center py-16 px-4">
                    <div class="bg-white p-8 rounded-xl shadow-2xl max-w-4xl mx-auto">
                        <h2 class="text-5xl font-extrabold text-green-700 mb-6 leading-tight">
                            Ever-BU: Dari Bumi, untuk Hidup Sehat Berkelanjutan!
                        </h2>
                        <p class="text-lg text-gray-700 mb-8 max-w-2xl mx-auto">
                            Ever-BU adalah brand inovatif di bidang kuliner dan agrobisnis, fokus pada pemanfaatan labu kuning secara holistik. Kami mengubah labu kuning yang kaya nutrisi menjadi berbagai produk bernilai tinggi, sekaligus meminimalkan limbah.
                        </p>

                        <!-- Zero Waste Section -->
                        <div class="mt-12 bg-yellow-50 p-8 rounded-xl shadow-inner border border-yellow-200">
                            <h3 class="text-3xl font-bold text-yellow-700 mb-6">Pendekatan Zero Waste Kami</h3>
                            <p class="text-md text-gray-600 mb-6">
                                Di Ever-BU, kami berkomitmen pada pendekatan zero waste, memastikan setiap bagian labu kuning dioptimalkan nilainya. Ini adalah siklus berkelanjutan kami:
                            </p>
                            <div class="grid md:grid-cols-3 gap-8 text-left">
                                <div class="flex flex-col items-center p-4 bg-white rounded-lg shadow-md border border-green-100">
                                    <span class="text-5xl mb-4">🎃</span>
                                    <h4 class="text-xl font-semibold text-green-600 mb-2">Pemanfaatan Buah</h4>
                                    <p class="text-gray-600 text-sm">Daging labu kuning diolah menjadi sereal bergizi tinggi, "PumpCrunch".</p>
                                </div>
                                <div class="flex flex-col items-center p-4 bg-white rounded-lg shadow-md border border-green-100">
                                    <span class="text-5xl mb-4">🌱</span>
                                    <h4 class="text-xl font-semibold text-green-600 mb-2">Pemanfaatan Biji</h4>
                                    <p class="text-gray-600 text-sm">Biji labu dipanggang menjadi camilan sehat aneka rasa, "SeedChew".</p>
                                </div>
                                <div class="flex flex-col items-center p-4 bg-white rounded-lg shadow-md border border-green-100">
                                    <span class="text-5xl mb-4">♻️</span>
                                    <h4 class="text-xl font-semibold text-green-600 mb-2">Pemanfaatan Limbah</h4>
                                    <p class="text-gray-600 text-sm">Sisa olahan labu diubah menjadi pupuk organik cair "EcoGrow" untuk pertanian berkelanjutan.</p>
                                </div>
                            </div>
                            <p class="text-md text-gray-600 mt-6">
                                Dengan ini, kami tidak hanya menciptakan produk inovatif tetapi juga berkontribusi pada keberlanjutan lingkungan dan ekosistem pangan yang lebih sehat.
                            </p>
                        </div>

                        <button
                            onclick="navigateTo('products')"
                            class="mt-12 bg-green-500 hover:bg-green-600 text-white text-xl font-bold px-8 py-4 rounded-full shadow-lg transform hover:scale-105 transition-all duration-300"
                        >
                            Lihat Produk Kami
                        </button>
                    </div>
                </section>
            `;
        }

        function renderProductsPage() {
            let productsHtml = productsData.map(product => `
                <div class="bg-white rounded-xl shadow-xl overflow-hidden transform hover:scale-105 transition-all duration-300 border border-yellow-100">
                    <img src="${product.image}" alt="${product.name}" class="w-full h-56 object-cover" />
                    <div class="p-6">
                        <h3 class="text-2xl font-bold text-green-600 mb-2">${product.name}</h3>
                        <p class="text-gray-700 mb-4 text-sm">${product.description}</p>
                        <div class="flex justify-between items-center">
                            <span class="text-2xl font-extrabold text-yellow-700">
                                ${formatCurrency(product.price)}
                            </span>
                            <button
                                onclick="addToCart(${product.id})"
                                class="bg-yellow-500 hover:bg-yellow-600 text-white px-6 py-3 rounded-full shadow-md transform hover:scale-105 transition-all duration-300 flex items-center space-x-2"
                            >
                                <!-- SVG for add to cart icon -->
                                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-plus-circle">
                                    <circle cx="12" cy="12" r="10" />
                                    <path d="M8 12h8" />
                                    <path d="M12 8v8" />
                                </svg>
                                <span>Tambah ke Keranjang</span>
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');

            mainContentDiv.innerHTML = `
                <section class="py-12 px-4">
                    <h2 class="text-4xl font-bold text-center text-green-700 mb-10">Produk Unggulan Ever-BU</h2>
                    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                        ${productsHtml}
                    </div>
                </section>
            `;
        }

        function renderCartPage() {
            const total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);
            let cartItemsHtml = '';

            if (cart.length === 0) {
                cartItemsHtml = `
                    <div class="bg-white p-8 rounded-xl shadow-lg text-center max-w-2xl mx-auto">
                        <p class="text-xl text-gray-600 mb-4">Keranjang Anda kosong.</p>
                        <button
                            onclick="navigateTo('products')"
                            class="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-full shadow-md transform hover:scale-105 transition-all duration-300"
                        >
                            Mulai Belanja
                        </button>
                    </div>
                `;
            } else {
                cartItemsHtml = `
                    <div class="bg-white p-8 rounded-xl shadow-xl max-w-4xl mx-auto">
                        <div class="space-y-6 mb-8">
                            ${cart.map(item => `
                                <div class="flex items-center justify-between border-b pb-4 last:border-b-0">
                                    <div class="flex items-center space-x-4">
                                        <img src="${item.image}" alt="${item.name}" class="w-20 h-20 object-cover rounded-lg shadow-md" />
                                        <div>
                                            <h3 class="text-xl font-semibold text-green-600">${item.name}</h3>
                                            <p class="text-gray-600">${formatCurrency(item.price)}</p>
                                        </div>
                                    </div>
                                    <div class="flex items-center space-x-4">
                                        <div class="flex items-center border border-gray-300 rounded-md">
                                            <button
                                                onclick="updateQuantity(${item.id}, ${item.quantity - 1})"
                                                class="px-3 py-1 bg-gray-100 hover:bg-gray-200 rounded-l-md"
                                            >
                                                -
                                            </button>
                                            <span class="px-4 py-1 text-lg font-medium">${item.quantity}</span>
                                            <button
                                                onclick="updateQuantity(${item.id}, ${item.quantity + 1})"
                                                class="px-3 py-1 bg-gray-100 hover:bg-gray-200 rounded-r-md"
                                            >
                                                +
                                            </button>
                                        </div>
                                        <button
                                            onclick="removeFromCart(${item.id})"
                                            class="text-red-500 hover:text-red-700 transition-colors duration-300 p-2 rounded-full hover:bg-red-100"
                                        >
                                            <!-- Trash Icon SVG -->
                                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-trash-2">
                                                <path d="M3 6h18" />
                                                <path d="M19 6v14c0 1-1 2-2 2H7c-1 0-2-1-2-2V6" />
                                                <path d="M8 6V4c0-1 1-2 2-2h4c1 0 2 1 2 2v2" />
                                                <line x1="10" x2="10" y1="11" y2="17" />
                                                <line x1="14" x2="14" y1="11" y2="17" />
                                            </svg>
                                        </button>
                                    </div>
                                </div>
                            `).join('')}
                        </div>

                        <div class="flex justify-between items-center border-t pt-6 mt-6">
                            <h3 class="text-2xl font-bold text-green-700">Total:</h3>
                            <span class="text-3xl font-extrabold text-yellow-700">
                                ${formatCurrency(total)}
                            </span>
                        </div>

                        <div class="flex justify-end space-x-4 mt-8">
                            <button
                                onclick="clearCart()"
                                class="bg-gray-300 hover:bg-gray-400 text-gray-800 px-6 py-3 rounded-full shadow-md transition-all duration-300"
                            >
                                Kosongkan Keranjang
                            </button>
                            <button
                                onclick="navigateTo('checkout')"
                                class="bg-green-500 hover:bg-green-600 text-white px-8 py-3 rounded-full shadow-lg transform hover:scale-105 transition-all duration-300"
                            >
                                Lanjutkan ke Pembayaran
                            </button>
                        </div>
                    </div>
                `;
            }

            mainContentDiv.innerHTML = `
                <section class="py-12 px-4">
                    <h2 class="text-4xl font-bold text-center text-green-700 mb-10">Keranjang Belanja Anda</h2>
                    ${cartItemsHtml}
                </section>
            `;
        }

        function renderCheckoutPage() {
            if (!isLoggedIn) {
                showNotification('Anda perlu login untuk melanjutkan pembayaran.', 'info');
                navigateTo('login');
                return;
            }

            if (cart.length === 0) {
                showNotification('Keranjang Anda kosong. Tambahkan produk sebelum checkout.', 'error');
                navigateTo('products');
                return;
            }

            const total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);
            let orderSummaryHtml = cart.map(item => `
                <li class="flex justify-between items-center py-2 border-b last:border-b-0">
                    <span class="text-gray-700">${item.name} (x${item.quantity})</span>
                    <span class="font-semibold">${formatCurrency(item.price * item.quantity)}</span>
                </li>
            `).join('');

            mainContentDiv.innerHTML = `
                <section class="py-12 px-4">
                    <h2 class="text-4xl font-bold text-center text-green-700 mb-10">Pembayaran</h2>

                    <div class="bg-white p-8 rounded-xl shadow-xl max-w-3xl mx-auto">
                        <form id="checkout-form">
                            <!-- Order Summary -->
                            <h3 class="text-2xl font-bold text-green-600 mb-4">Ringkasan Pesanan</h3>
                            <ul class="mb-6 border rounded-lg p-4 bg-gray-50">
                                ${orderSummaryHtml}
                                <li class="flex justify-between items-center py-2 font-bold text-xl text-green-800">
                                    <span>Total:</span>
                                    <span>${formatCurrency(total)}</span>
                                </li>
                            </ul>

                            <!-- Shipping Address -->
                            <h3 class="text-2xl font-bold text-green-600 mb-4 mt-8">Alamat Pengiriman</h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
                                <div>
                                    <label for="shipping-name" class="block text-gray-700 text-sm font-bold mb-2">Nama Lengkap</label>
                                    <input
                                        type="text"
                                        id="shipping-name"
                                        name="name"
                                        value="${currentUser ? currentUser.name : ''}"
                                        class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                        required
                                    />
                                </div>
                                <div>
                                    <label for="shipping-phone" class="block text-gray-700 text-sm font-bold mb-2">Nomor Telepon</label>
                                    <input
                                        type="tel"
                                        id="shipping-phone"
                                        name="phone"
                                        class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                        required
                                    />
                                </div>
                                <div class="md:col-span-2">
                                    <label for="shipping-address" class="block text-gray-700 text-sm font-bold mb-2">Alamat Lengkap</label>
                                    <textarea
                                        id="shipping-address"
                                        name="address"
                                        rows="3"
                                        class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                        required
                                    ></textarea>
                                </div>
                                <div>
                                    <label for="shipping-city" class="block text-gray-700 text-sm font-bold mb-2">Kota</label>
                                    <input
                                        type="text"
                                        id="shipping-city"
                                        name="city"
                                        class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                        required
                                    />
                                </div>
                                <div>
                                    <label for="shipping-postalCode" class="block text-gray-700 text-sm font-bold mb-2">Kode Pos</label>
                                    <input
                                        type="text"
                                        id="shipping-postalCode"
                                        name="postalCode"
                                        class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                        required
                                    />
                                </div>
                            </div>

                            <!-- Payment Method -->
                            <h3 class="text-2xl font-bold text-green-600 mb-4 mt-8">Metode Pembayaran</h3>
                            <div class="space-y-4 mb-8">
                                <label class="flex items-center bg-gray-50 p-4 rounded-lg shadow-sm cursor-pointer border border-gray-200 hover:border-yellow-500 transition-colors duration-200">
                                    <input
                                        type="radio"
                                        name="paymentMethod"
                                        value="bank_transfer"
                                        checked
                                        class="form-radio h-5 w-5 text-yellow-600"
                                    />
                                    <span class="ml-3 text-lg font-medium text-gray-800">Transfer Bank</span>
                                    <p class="ml-auto text-sm text-gray-500">BCA: 123-456-7890 (a.n. Ever-BU)</p>
                                </label>
                                <label class="flex items-center bg-gray-50 p-4 rounded-lg shadow-sm cursor-pointer border border-gray-200 hover:border-yellow-500 transition-colors duration-200">
                                    <input
                                        type="radio"
                                        name="paymentMethod"
                                        value="e_wallet"
                                        class="form-radio h-5 w-5 text-yellow-600"
                                    />
                                    <span class="ml-3 text-lg font-medium text-gray-800">E-Wallet</span>
                                    <p class="ml-auto text-sm text-gray-500">OVO / GoPay / Dana</p>
                                </label>
                                <label class="flex items-center bg-gray-50 p-4 rounded-lg shadow-sm cursor-pointer border border-gray-200 hover:border-yellow-500 transition-colors duration-200">
                                    <input
                                        type="radio"
                                        name="paymentMethod"
                                        value="credit_card"
                                        class="form-radio h-5 w-5 text-yellow-600"
                                    />
                                    <span class="ml-3 text-lg font-medium text-gray-800">Kartu Kredit/Debit</span>
                                    <p class="ml-auto text-sm text-gray-500">Visa / Mastercard</p>
                                </label>
                            </div>

                            <button
                                type="submit"
                                class="w-full bg-green-500 hover:bg-green-600 text-white text-xl font-bold px-8 py-4 rounded-full shadow-lg transform hover:scale-105 transition-all duration-300"
                            >
                                Konfirmasi Pesanan
                            </button>
                        </form>
                    </div>
                </section>
            `;

            // Add event listener for the form submission
            document.getElementById('checkout-form').addEventListener('submit', handleCheckoutSubmit);

            // Pre-fill name if logged in
            if (currentUser && currentUser.name) {
                document.getElementById('shipping-name').value = currentUser.name;
            }
        }

        function handleCheckoutSubmit(event) {
            event.preventDefault();

            const form = event.target;
            const shippingAddress = {
                name: form.elements['name'].value,
                address: form.elements['address'].value,
                city: form.elements['city'].value,
                postalCode: form.elements['postalCode'].value,
                phone: form.elements['phone'].value,
            };
            const paymentMethod = form.elements['paymentMethod'].value;

            if (!isLoggedIn) {
                showNotification('Silakan login terlebih dahulu.', 'error');
                navigateTo('login');
                return;
            }

            if (cart.length === 0) {
                showNotification('Keranjang Anda kosong. Tambahkan produk sebelum checkout.', 'error');
                navigateTo('products');
                return;
            }

            // Simple validation
            if (Object.values(shippingAddress).some(val => val === '')) {
                showNotification('Mohon lengkapi semua detail alamat pengiriman.', 'error');
                return;
            }

            // Simulate order placement
            console.log('Pesanan ditempatkan:', {
                items: cart,
                total: cart.reduce((sum, item) => sum + item.price * item.quantity, 0),
                shippingAddress,
                paymentMethod,
                user: currentUser,
            });

            // Render order confirmation page
            mainContentDiv.innerHTML = `
                <section class="py-12 px-4 text-center">
                    <div class="bg-white p-8 rounded-xl shadow-lg max-w-xl mx-auto">
                        <h2 class="text-4xl font-bold text-green-700 mb-6">Terima Kasih!</h2>
                        <p class="text-xl text-gray-700 mb-4">Pesanan Anda telah berhasil ditempatkan.</p>
                        <p class="text-md text-gray-600 mb-8">
                            Kami akan segera memproses pesanan Anda dan mengirimkannya ke alamat:
                            <br />
                            <span class="font-semibold">${shippingAddress.address}, ${shippingAddress.city}, ${shippingAddress.postalCode}</span>
                        </p>
                        <button
                            onclick="navigateTo('home')"
                            class="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-full shadow-md transform hover:scale-105 transition-all duration-300"
                        >
                            Kembali ke Beranda
                        </button>
                    </div>
                </section>
            `;
            clearCart(); // Clear cart after order is placed
            showNotification('Pesanan Anda berhasil ditempatkan!', 'success');
        }


        function renderLoginPage() {
            mainContentDiv.innerHTML = `
                <section class="py-12 px-4 flex justify-center items-center">
                    <div class="bg-white p-8 rounded-xl shadow-xl max-w-md w-full">
                        <h2 id="login-register-title" class="text-4xl font-bold text-center text-green-700 mb-8">
                            Login ke Akun Anda
                        </h2>
                        <form id="login-form" class="space-y-6">
                            <div>
                                <label for="login-email" class="block text-gray-700 text-sm font-bold mb-2">Email</label>
                                <input
                                    type="email"
                                    id="login-email"
                                    class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                    placeholder="email@example.com"
                                    required
                                />
                            </div>
                            <div>
                                <label for="login-password" class="block text-gray-700 text-sm font-bold mb-2">Password</label>
                                <input
                                    type="password"
                                    id="login-password"
                                    class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                    placeholder="********"
                                    required
                                />
                            </div>
                            <button
                                type="submit"
                                id="login-submit-button"
                                class="w-full bg-green-500 hover:bg-green-600 text-white text-xl font-bold px-8 py-4 rounded-full shadow-lg transform hover:scale-105 transition-all duration-300"
                            >
                                Login
                            </button>
                        </form>
                        <div class="mt-6 text-center">
                            <button
                                onclick="toggleLoginRegister()"
                                id="toggle-auth-mode"
                                class="text-green-600 hover:text-green-800 font-semibold transition-colors duration-300"
                            >
                                Belum punya akun? Daftar di sini.
                            </button>
                        </div>
                        <p class="text-center text-sm text-gray-500 mt-4">
                            (Untuk demo, gunakan email: <span class="font-semibold">user@example.com</span>, password: <span class="font-semibold">password123</span>)
                        </p>
                    </div>
                </section>
            `;
            document.getElementById('login-form').addEventListener('submit', handleLoginSubmit);
        }

        let isRegisterMode = false;
        function toggleLoginRegister() {
            isRegisterMode = !isRegisterMode;
            const title = document.getElementById('login-register-title');
            const submitButton = document.getElementById('login-submit-button');
            const toggleButton = document.getElementById('toggle-auth-mode');

            if (title) title.textContent = isRegisterMode ? 'Daftar Akun' : 'Login ke Akun Anda';
            if (submitButton) submitButton.textContent = isRegisterMode ? 'Daftar' : 'Login';
            if (toggleButton) toggleButton.textContent = isRegisterMode ? 'Sudah punya akun? Login di sini.' : 'Belum punya akun? Daftar di sini.';
        }

        function handleLoginSubmit(event) {
            event.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;

            if (isRegisterMode) {
                console.log('Mendaftar dengan:', { email, password });
                showNotification('Pendaftaran berhasil! Silakan login.', 'success');
                isRegisterMode = false; // Switch back to login mode
                renderLoginPage(); // Re-render to update UI
            } else {
                if (email === 'user@example.com' && password === 'password123') {
                    isLoggedIn = true;
                    currentUser = { name: 'Pengguna Ever-BU', email: email };
                    showNotification('Login berhasil!', 'success');
                    navigateTo('home');
                } else {
                    showNotification('Email atau password salah.', 'error');
                }
            }
            updateAuthButton();
        }

        function renderContactPage() {
            mainContentDiv.innerHTML = `
                <section class="py-12 px-4">
                    <h2 class="text-4xl font-bold text-center text-green-700 mb-10">Hubungi Kami</h2>

                    <div class="bg-white p-8 rounded-xl shadow-xl max-w-4xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-8">
                        <!-- Contact Form -->
                        <div>
                            <h3 class="text-2xl font-bold text-green-600 mb-4">Kirim Pesan kepada Kami</h3>
                            <form id="contact-form" class="space-y-4">
                                <div>
                                    <label for="contact-name" class="block text-gray-700 text-sm font-bold mb-2">Nama Anda</label>
                                    <input
                                        type="text"
                                        id="contact-name"
                                        name="name"
                                        class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                        required
                                    />
                                </div>
                                <div>
                                    <label for="contact-email" class="block text-gray-700 text-sm font-bold mb-2">Email Anda</label>
                                    <input
                                        type="email"
                                        id="contact-email"
                                        name="email"
                                        class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                        required
                                    />
                                </div>
                                <div>
                                    <label for="contact-message" class="block text-gray-700 text-sm font-bold mb-2">Pesan Anda</label>
                                    <textarea
                                        id="contact-message"
                                        name="message"
                                        rows="5"
                                        class="shadow appearance-none border rounded-lg w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-yellow-500"
                                        required
                                    ></textarea>
                                </div>
                                <button
                                    type="submit"
                                    class="bg-green-500 hover:bg-green-600 text-white font-bold px-6 py-3 rounded-full shadow-md transform hover:scale-105 transition-all duration-300"
                                >
                                    Kirim Pesan
                                </button>
                            </form>
                        </div>

                        <!-- Contact Information -->
                        <div>
                            <h3 class="text-2xl font-bold text-green-600 mb-4">Informasi Kontak</h3>
                            <div class="space-y-4 text-gray-700">
                                <p class="flex items-center space-x-3">
                                    <!-- Mail Icon SVG -->
                                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-mail">
                                        <rect width="20" height="16" x="2" y="4" rx="2" />
                                        <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7" />
                                    </svg>
                                    <span>info@everbu.com</span>
                                </p>
                                <p class="flex items-center space-x-3">
                                    <!-- Phone Icon SVG -->
                                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-phone">
                                        <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-3.67-3.67A19.79 19.79 0 0 1 2 6.18 2 2 0 0 1 4.08 4h3a2 2 0 0 1 2 1.73c.21 1.02.36 2.07.46 3.12a2 2 0 0 1-1.15 2.06l-.44.22a22.39 22.39 0 0 0 9.14 9.14l.22-.44a2 2 0 0 1 2.06-1.15h3a2 2 0 0 1 2 2Z" />
                                    </svg>
                                    <span>+62 812-3456-7890</span>
                                </p>
                                <p class="flex items-start space-x-3">
                                    <!-- Map Pin Icon SVG -->
                                    <svg xmlns="http://www.w3.org/2000/svg" width="60" height="60" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" class="lucide lucide-map-pin">
                                        <path d="M12 18.3a3 3 0 1 0 0-6 3 3 0 0 0 0 6Z" />
                                        <path d="M12 22c-4.97 0-9-4.03-9-9a9 9 0 0 1 18 0c0 4.97-4.03 9-9 9Z" />
                                    </svg>
                                    <span>Jl. Pandega Sakti No. 1 A, Kentungan, Condongcatur, Kecamatan Depok, Kabupaten Sleman, Daerah Istimewa Yogyakarta, Indonesia</span>
                                </p>
                            </div>

                            <div class="mt-8">
                                <h3 class="text-2xl font-bold text-green-600 mb-4">Temukan Kami di Peta</h3>
                                <!-- Placeholder for map -->
                                <img src= "gmaps ever-bu.jpeg" height= "150px" width= "300px">
                                </div>
                            </div>
                        </div>
                    </div>
                </section>
            `;
            document.getElementById('contact-form').addEventListener('submit', handleContactSubmit);
        }

        function handleContactSubmit(event) {
            event.preventDefault();
            const formData = {
                name: document.getElementById('contact-name').value,
                email: document.getElementById('contact-email').value,
                message: document.getElementById('contact-message').value,
            };
            console.log('Form Kontak Dikirim:', formData);
            showNotification('Pesan Anda telah terkirim!', 'success');
            // Reset form
            document.getElementById('contact-name').value = '';
            document.getElementById('contact-email').value = '';
            document.getElementById('contact-message').value = '';
        }


        // Navigation function
        function navigateTo(page) {
            currentPage = page;
            updateNavStyles();
            switch (page) {
                case 'home':
                    renderHomePage();
                    break;
                case 'products':
                    renderProductsPage();
                    break;
                case 'cart':
                    renderCartPage();
                    break;
                case 'checkout':
                    renderCheckoutPage();
                    break;
                case 'login':
                    renderLoginPage();
                    break;
                case 'contact':
                    renderContactPage();
                    break;
                default:
                    renderHomePage();
            }
        }

        // Initial load
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('current-year').textContent = new Date().getFullYear();
            navigateTo('home'); // Load home page initially
            updateCartItemCount(); // Initialize cart count
            updateAuthButton(); // Initialize auth button state
        });
    </script>
</body>
</html>
