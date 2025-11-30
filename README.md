<!DOCTYPE html>
<html lang="es">
<head>
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-11ZKSYXZBE"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-11ZKSYXZBE');
</script>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="theme-color" content="#FFE600">
    <title>AutoRent - Renta de Vehículos</title>
    <!-- PWA Meta Tags -->
    <link rel="manifest" href="/manifest.json">
    <link rel="icon" type="image/png" sizes="192x192" href="https://utfs.io/f/5BN0V4mlt4NU0VoS5bBeXK1e7fx2toMJsnUB0SuRjmzqgk85">
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #FFE600;
            --dark: #000000;
            --light: #FFFFFF;
            --gray: #F5F5F5;
            --gray-dark: #333333;
            --shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            --radius: 12px;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--gray);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header Styles */
        header {
            background-color: var(--primary);
            padding: 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-weight: bold;
            font-size: 1.25rem;
        }

        .logo img {
            height: 32px;
            width: 32px;
        }

        .header-actions {
            display: flex;
            gap: 1rem;
        }

        .header-btn {
            background: none;
            border: none;
            font-size: 1.25rem;
            cursor: pointer;
            position: relative;
            color: var(--dark);
            transition: var(--transition);
            padding: 0.5rem;
        }

        .cart-count {
            position: absolute;
            top: 0;
            right: 0;
            background-color: var(--dark);
            color: var(--light);
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 0.7rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Bottom Navigation */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background-color: var(--light);
            display: flex;
            justify-content: space-around;
            padding: 0.75rem 0;
            box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1);
            z-index: 90;
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 0.25rem;
            color: var(--gray-dark);
            font-size: 0.75rem;
            text-decoration: none;
            transition: var(--transition);
        }

        .nav-item.active {
            color: var(--dark);
        }

        .nav-item i {
            font-size: 1.25rem;
        }

        /* Main Content */
        .main-content {
            padding: 1rem;
            padding-bottom: 80px; /* Space for bottom nav */
        }

        /* Search Bar */
        .search-container {
            margin-bottom: 1.5rem;
        }

        .search-bar {
            position: relative;
            width: 100%;
        }

        .search-bar input {
            width: 100%;
            padding: 0.75rem 1rem 0.75rem 3rem;
            border: none;
            border-radius: 50px;
            box-shadow: var(--shadow);
            font-size: 1rem;
            background-color: var(--light);
        }

        .search-bar i {
            position: absolute;
            left: 1rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--gray-dark);
        }

        /* Filter Chips */
        .filter-chips {
            display: flex;
            gap: 0.5rem;
            overflow-x: auto;
            padding: 0.5rem 0;
            margin-bottom: 1rem;
            -ms-overflow-style: none;
            scrollbar-width: none;
        }

        .filter-chips::-webkit-scrollbar {
            display: none;
        }

        .filter-chip {
            background-color: var(--light);
            border: 1px solid #ddd;
            border-radius: 50px;
            padding: 0.5rem 1rem;
            font-size: 0.875rem;
            white-space: nowrap;
            transition: var(--transition);
        }

        .filter-chip.active {
            background-color: var(--primary);
            border-color: var(--primary);
        }

        /* Vehicles Grid */
        .vehicles-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
        }

        .vehicle-card {
            background-color: var(--light);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .vehicle-image {
            height: 180px;
            width: 100%;
            position: relative;
            overflow: hidden;
        }

        .vehicle-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .vehicle-price {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--primary);
            color: var(--dark);
            padding: 0.25rem 0.75rem;
            border-radius: 50px;
            font-weight: bold;
            font-size: 0.875rem;
        }

        .vehicle-details {
            padding: 1rem;
        }

        .vehicle-name {
            font-weight: bold;
            margin-bottom: 0.5rem;
            font-size: 1.125rem;
        }

        .vehicle-specs {
            display: flex;
            gap: 1rem;
            margin-bottom: 1rem;
            font-size: 0.875rem;
            color: var(--gray-dark);
        }

        .vehicle-spec {
            display: flex;
            align-items: center;
            gap: 0.25rem;
        }

        .vehicle-actions {
            display: flex;
            gap: 0.5rem;
        }

        .btn {
            padding: 0.75rem 1rem;
            border: none;
            border-radius: var(--radius);
            cursor: pointer;
            font-weight: bold;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            flex: 1;
        }

        .btn-primary {
            background-color: var(--primary);
            color: var(--dark);
        }

        .btn-primary:active {
            background-color: #ffd700;
            transform: scale(0.98);
        }

        .btn-secondary {
            background-color: var(--dark);
            color: var(--light);
        }

        .btn-secondary:active {
            background-color: #333;
            transform: scale(0.98);
        }

        /* Modal Styles */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: flex-end;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal {
            background-color: var(--light);
            border-radius: var(--radius) var(--radius) 0 0;
            width: 100%;
            max-height: 85vh;
            padding: 1.5rem;
            box-shadow: var(--shadow);
            transform: translateY(100%);
            transition: var(--transition);
            overflow-y: auto;
        }

        .modal-overlay.active .modal {
            transform: translateY(0);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .modal-title {
            font-weight: bold;
            font-size: 1.25rem;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--gray-dark);
        }

        .form-group {
            margin-bottom: 1.25rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: var(--radius);
            font-size: 1rem;
        }

        .checkbox-group {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.75rem;
        }

        .checkbox-group input {
            width: 18px;
            height: 18px;
        }

        .modal-actions {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }

        /* Cart Styles */
        .cart-item {
            display: flex;
            gap: 1rem;
            padding: 1rem 0;
            border-bottom: 1px solid #eee;
        }

        .cart-item-image {
            width: 80px;
            height: 60px;
            background-color: #ddd;
            border-radius: var(--radius);
            overflow: hidden;
            flex-shrink: 0;
        }

        .cart-item-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .cart-item-details {
            flex: 1;
        }

        .cart-item-name {
            font-weight: bold;
            margin-bottom: 0.25rem;
        }

        .cart-item-price {
            color: var(--gray-dark);
            font-size: 0.875rem;
        }

        .cart-item-actions {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .quantity-btn {
            background: none;
            border: 1px solid #ddd;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            margin-top: 1.5rem;
            padding-top: 1rem;
            border-top: 2px solid #eee;
            font-weight: bold;
            font-size: 1.125rem;
        }

        /* Filter Modal */
        .filter-modal .modal {
            max-height: 90vh;
        }

        .filter-group {
            margin-bottom: 1.5rem;
        }

        .filter-title {
            font-weight: bold;
            margin-bottom: 0.75rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .filter-options {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .filter-option {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            cursor: pointer;
            padding: 0.5rem 0;
            transition: var(--transition);
        }

        .filter-option:hover {
            color: var(--primary);
        }

        .filter-count {
            color: var(--gray-dark);
            font-size: 0.875rem;
        }

        /* Swipeable Tabs */
        .tabs {
            display: flex;
            border-bottom: 1px solid #eee;
            margin-bottom: 1rem;
            overflow-x: auto;
            -ms-overflow-style: none;
            scrollbar-width: none;
        }

        .tabs::-webkit-scrollbar {
            display: none;
        }

        .tab {
            padding: 0.75rem 1rem;
            white-space: nowrap;
            font-weight: 500;
            border-bottom: 2px solid transparent;
            transition: var(--transition);
        }

        .tab.active {
            border-bottom-color: var(--primary);
            color: var(--primary);
        }

        /* Swipe Indicators */
        .swipe-indicators {
            display: flex;
            justify-content: center;
            gap: 0.5rem;
            margin: 1rem 0;
        }

        .indicator {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background-color: #ddd;
            transition: var(--transition);
        }

        .indicator.active {
            background-color: var(--primary);
            transform: scale(1.2);
        }

        /* Animation for touch feedback */
        .touch-feedback:active {
            transform: scale(0.98);
        }

        /* Loading Animation */
        .loading {
            display: flex;
            justify-content: center;
            padding: 2rem;
        }

        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid rgba(0, 0, 0, 0.1);
            border-left-color: var(--primary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Empty State */
        .empty-state {
            text-align: center;
            padding: 2rem;
            color: var(--gray-dark);
        }

        .empty-state i {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #ddd;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <button class="header-btn" id="menu-btn">
            <i class="fas fa-bars"></i>
        </button>
        <div class="logo">
            <img src="https://utfs.io/f/5BN0V4mlt4NU0VoS5bBeXK1e7fx2toMJsnUB0SuRjmzqgk85" alt="AutoRent Logo">
            <span>AutoRent</span>
        </div>
        <div class="header-actions">
            <button class="header-btn" id="cart-btn">
                <i class="fas fa-shopping-cart"></i>
                <span class="cart-count">2</span>
            </button>
        </div>
    </header>

    <!-- Main Content -->
    <main class="main-content">
        <!-- Search Bar -->
        <div class="search-container">
            <div class="search-bar">
                <i class="fas fa-search"></i>
                <input type="text" placeholder="Buscar vehículos...">
            </div>
        </div>

        <!-- Filter Chips -->
        <div class="filter-chips">
            <div class="filter-chip active">Todos</div>
            <div class="filter-chip">Económicos</div>
            <div class="filter-chip">SUV</div>
            <div class="filter-chip">Deportivos</div>
            <div class="filter-chip">Lujo</div>
            <div class="filter-chip">Automáticos</div>
        </div>

        <!-- Vehicles Grid -->
        <div class="vehicles-grid">
            <!-- Vehicle Card 1 -->
            <div class="vehicle-card touch-feedback">
                <div class="vehicle-image">
                    <img src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="Toyota Corolla">
                    <div class="vehicle-price">$45/día</div>
                </div>
                <div class="vehicle-details">
                    <div class="vehicle-name">Toyota Corolla 2023</div>
                    <div class="vehicle-specs">
                        <div class="vehicle-spec">
                            <i class="fas fa-user"></i>
                            <span>5 pasajeros</span>
                        </div>
                        <div class="vehicle-spec">
                            <i class="fas fa-car"></i>
                            <span>Automática</span>
                        </div>
                    </div>
                    <div class="vehicle-actions">
                        <button class="btn btn-primary add-to-cart touch-feedback">
                            <i class="fas fa-cart-plus"></i>
                            Agregar
                        </button>
                        <button class="btn btn-secondary touch-feedback">
                            <i class="fas fa-info-circle"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Vehicle Card 2 -->
            <div class="vehicle-card touch-feedback">
                <div class="vehicle-image">
                    <img src="https://images.unsplash.com/photo-1553440569-bcc63803a83d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1025&q=80" alt="Honda CR-V">
                    <div class="vehicle-price">$65/día</div>
                </div>
                <div class="vehicle-details">
                    <div class="vehicle-name">Honda CR-V 2023</div>
                    <div class="vehicle-specs">
                        <div class="vehicle-spec">
                            <i class="fas fa-user"></i>
                            <span>5 pasajeros</span>
                        </div>
                        <div class="vehicle-spec">
                            <i class="fas fa-car"></i>
                            <span>Automática</span>
                        </div>
                    </div>
                    <div class="vehicle-actions">
                        <button class="btn btn-primary add-to-cart touch-feedback">
                            <i class="fas fa-cart-plus"></i>
                            Agregar
                        </button>
                        <button class="btn btn-secondary touch-feedback">
                            <i class="fas fa-info-circle"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Vehicle Card 3 -->
            <div class="vehicle-card touch-feedback">
                <div class="vehicle-image">
                    <img src="https://images.unsplash.com/photo-1555215695-3004980ad54e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="BMW X5">
                    <div class="vehicle-price">$120/día</div>
                </div>
                <div class="vehicle-details">
                    <div class="vehicle-name">BMW X5 2023</div>
                    <div class="vehicle-specs">
                        <div class="vehicle-spec">
                            <i class="fas fa-user"></i>
                            <span>5 pasajeros</span>
                        </div>
                        <div class="vehicle-spec">
                            <i class="fas fa-car"></i>
                            <span>Automática</span>
                        </div>
                    </div>
                    <div class="vehicle-actions">
                        <button class="btn btn-primary add-to-cart touch-feedback">
                            <i class="fas fa-cart-plus"></i>
                            Agregar
                        </button>
                        <button class="btn btn-secondary touch-feedback">
                            <i class="fas fa-info-circle"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Swipe Indicators -->
        <div class="swipe-indicators">
            <div class="indicator active"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
        </div>
    </main>

    <!-- Bottom Navigation -->
    <nav class="bottom-nav">
        <a href="#" class="nav-item active">
            <i class="fas fa-home"></i>
            <span>Inicio</span>
        </a>
        <a href="#" class="nav-item">
            <i class="fas fa-search"></i>
            <span>Buscar</span>
        </a>
        <a href="#" class="nav-item" id="filter-btn">
            <i class="fas fa-filter"></i>
            <span>Filtros</span>
        </a>
        <a href="#" class="nav-item">
            <i class="fas fa-heart"></i>
            <span>Favoritos</span>
        </a>
        <a href="#" class="nav-item" id="profile-btn">
            <i class="fas fa-user"></i>
            <span>Perfil</span>
        </a>
    </nav>

    <!-- Cart Modal -->
    <div class="modal-overlay" id="cart-modal">
        <div class="modal">
            <div class="modal-header">
                <div class="modal-title">Tu Carrito de Renta</div>
                <button class="close-modal">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="modal-body">
                <div class="cart-item">
                    <div class="cart-item-image">
                        <img src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="Toyota Corolla">
                    </div>
                    <div class="cart-item-details">
                        <div class="cart-item-name">Toyota Corolla 2023</div>
                        <div class="cart-item-price">$45/día</div>
                    </div>
                    <div class="cart-item-actions">
                        <button class="quantity-btn touch-feedback">
                            <i class="fas fa-minus"></i>
                        </button>
                        <span>1</span>
                        <button class="quantity-btn touch-feedback">
                            <i class="fas fa-plus"></i>
                        </button>
                    </div>
                </div>
                <div class="cart-item">
                    <div class="cart-item-image">
                        <img src="https://images.unsplash.com/photo-1553440569-bcc63803a83d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1025&q=80" alt="Honda CR-V">
                    </div>
                    <div class="cart-item-details">
                        <div class="cart-item-name">Honda CR-V 2023</div>
                        <div class="cart-item-price">$65/día</div>
                    </div>
                    <div class="cart-item-actions">
                        <button class="quantity-btn touch-feedback">
                            <i class="fas fa-minus"></i>
                        </button>
                        <span>1</span>
                        <button class="quantity-btn touch-feedback">
                            <i class="fas fa-plus"></i>
                        </button>
                    </div>
                </div>
                <div class="cart-total">
                    <span>Total:</span>
                    <span>$110/día</span>
                </div>
                <div class="modal-actions">
                    <button class="btn btn-secondary touch-feedback">Seguir Explorando</button>
                    <button class="btn btn-primary touch-feedback">Proceder al Pago</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Filter Modal -->
    <div class="modal-overlay filter-modal" id="filter-modal">
        <div class="modal">
            <div class="modal-header">
                <div class="modal-title">Filtrar Vehículos</div>
                <button class="close-modal">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="modal-body">
                <div class="filter-group">
                    <div class="filter-title">
                        <span>Precio</span>
                    </div>
                    <div class="filter-options">
                        <div class="filter-option">
                            <input type="checkbox" id="price1">
                            <label for="price1">$0 - $50/día</label>
                            <span class="filter-count">(12)</span>
                        </div>
                        <div class="filter-option">
                            <input type="checkbox" id="price2">
                            <label for="price2">$51 - $100/día</label>
                            <span class="filter-count">(8)</span>
                        </div>
                        <div class="filter-option">
                            <input type="checkbox" id="price3">
                            <label for="price3">$101 - $150/día</label>
                            <span class="filter-count">(5)</span>
                        </div>
                        <div class="filter-option">
                            <input type="checkbox" id="price4">
                            <label for="price4">$151+ /día</label>
                            <span class="filter-count">(3)</span>
                        </div>
                    </div>
                </div>

                <div class="filter-group">
                    <div class="filter-title">
                        <span>Marca</span>
                    </div>
                    <div class="filter-options">
                        <div class="filter-option">
                            <input type="checkbox" id="brand1">
                            <label for="brand1">Toyota</label>
                            <span class="filter-count">(5)</span>
                        </div>
                        <div class="filter-option">
                            <input type="checkbox" id="brand2">
                            <label for="brand2">Honda</label>
                            <span class="filter-count">(4)</span>
                        </div>
                        <div class="filter-option">
                            <input type="checkbox" id="brand3">
                            <label for="brand3">Ford</label>
                            <span class="filter-count">(3)</span>
                        </div>
                    </div>
                </div>

                <div class="filter-group">
                    <div class="filter-title">
                        <span>Tipo de Vehículo</span>
                    </div>
                    <div class="filter-options">
                        <div class="filter-option">
                            <input type="checkbox" id="type1">
                            <label for="type1">Sedán</label>
                            <span class="filter-count">(6)</span>
                        </div>
                        <div class="filter-option">
                            <input type="checkbox" id="type2">
                            <label for="type2">SUV</label>
                            <span class="filter-count">(8)</span>
                        </div>
                        <div class="filter-option">
                            <input type="checkbox" id="type3">
                            <label for="type3">Deportivo</label>
                            <span class="filter-count">(4)</span>
                        </div>
                    </div>
                </div>

                <div class="modal-actions">
                    <button class="btn btn-secondary touch-feedback">Limpiar</button>
                    <button class="btn btn-primary touch-feedback">Aplicar Filtros</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Login Modal -->
    <div class="modal-overlay" id="login-modal">
        <div class="modal">
            <div class="modal-header">
                <div class="modal-title">Iniciar Sesión</div>
                <button class="close-modal">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label for="email">Correo Electrónico</label>
                    <input type="email" id="email" class="form-control" placeholder="tu@email.com">
                </div>
                <div class="form-group">
                    <label for="password">Contraseña</label>
                    <input type="password" id="password" class="form-control" placeholder="••••••••">
                </div>
                <div class="checkbox-group">
                    <input type="checkbox" id="remember">
                    <label for="remember">Recordarme</label>
                </div>
                <div class="modal-actions">
                    <button class="btn btn-primary touch-feedback">Iniciar Sesión</button>
                </div>
                <div style="text-align: center; margin-top: 1rem;">
                    <a href="#" style="color: var(--dark);">¿Olvidaste tu contraseña?</a>
                </div>
                <div style="text-align: center; margin-top: 0.5rem;">
                    <span>¿No tienes cuenta? </span>
                    <a href="#" style="color: var(--dark); font-weight: bold;">Regístrate</a>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Modal functionality
        document.addEventListener('DOMContentLoaded', function() {
            // Get modal elements
            const cartModal = document.getElementById('cart-modal');
            const filterModal = document.getElementById('filter-modal');
            const loginModal = document.getElementById('login-modal');
            
            // Get button elements
            const cartBtn = document.getElementById('cart-btn');
            const filterBtn = document.getElementById('filter-btn');
            const profileBtn = document.getElementById('profile-btn');
            const closeButtons = document.querySelectorAll('.close-modal');
            const addToCartButtons = document.querySelectorAll('.add-to-cart');
            
            // Open modals
            cartBtn.addEventListener('click', () => toggleModal(cartModal));
            filterBtn.addEventListener('click', () => toggleModal(filterModal));
            profileBtn.addEventListener('click', () => toggleModal(loginModal));
            
            // Close modals
            closeButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const modal = this.closest('.modal-overlay');
                    toggleModal(modal);
                });
            });
            
            // Close modal when clicking outside
            document.addEventListener('click', function(event) {
                if (event.target.classList.contains('modal-overlay')) {
                    toggleModal(event.target);
                }
            });
            
            // Add to cart functionality
            addToCartButtons.forEach(button => {
                button.addEventListener('click', function() {
                    // Simple animation feedback
                    this.style.transform = 'scale(0.95)';
                    setTimeout(() => {
                        this.style.transform = 'scale(1)';
                    }, 150);
                    
                    // Update cart count
                    const cartCount = document.querySelector('.cart-count');
                    let count = parseInt(cartCount.textContent);
                    cartCount.textContent = count + 1;
                    
                    // Show confirmation (in a real app, this would add the item to cart)
                    alert('Vehículo agregado al carrito');
                });
            });
            
            // Filter chips functionality
            const filterChips = document.querySelectorAll('.filter-chip');
            filterChips.forEach(chip => {
                chip.addEventListener('click', function() {
                    filterChips.forEach(c => c.classList.remove('active'));
                    this.classList.add('active');
                });
            });
            
            // Bottom nav active state
            const navItems = document.querySelectorAll('.nav-item');
            navItems.forEach(item => {
                item.addEventListener('click', function(e) {
                    e.preventDefault();
                    navItems.forEach(i => i.classList.remove('active'));
                    this.classList.add('active');
                });
            });
            
            // Function to toggle modal
            function toggleModal(modal) {
                modal.classList.toggle('active');
                document.body.style.overflow = modal.classList.contains('active') ? 'hidden' : 'auto';
            }
            
            // Touch feedback for all interactive elements
            const touchElements = document.querySelectorAll('.touch-feedback');
            touchElements.forEach(element => {
                element.addEventListener('touchstart', function() {
                    this.style.opacity = '0.7';
                });
                
                element.addEventListener('touchend', function() {
                    this.style.opacity = '1';
                });
            });
        });
    </script>
</body>
</html>
