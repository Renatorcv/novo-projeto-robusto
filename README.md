<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CheckList Pro - Gestão Inteligente</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/feather-icons/dist/feather.min.js"></script>
    <script src="https://unpkg.com/feather-icons"></script>
    <script src="https://cdn.jsdelivr.net/npm/vanta@latest/dist/vanta.globe.min.js"></script>
    <script>
      tailwind.config = {
        darkMode: 'class',
        theme: {
          extend: {
            colors: {
              primary: {
                50: '#eff6ff',
                100: '#dbeafe',
                200: '#bfdbfe',
                300: '#93c5fd',
                400: '#60a5fa',
                500: '#3b8ff8',
                600: '#2582f7',
                700: '#1d70ec',
                800: '#1e5fd0',
                900: '#1e4aa7',
              }
            }
          }
        }
      }
    </script>
    <style>
      html {
        scroll-behavior: smooth;
      }
      body {
        overflow-x: hidden;
      }
      #vanta-bg {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 0;
      }
      .primary-gradient-text {
        background: linear-gradient(90deg, #3b8ff8 0%, #7d53f8 100%);
        -webkit-background-clip: text;
        background-clip: text;
        color: transparent;
      }
      .nav-link {
        position: relative;
      }
      .nav-link::after {
        content: '';
        position: absolute;
        bottom: -2px;
        left: 0;
        width: 0;
        height: 2px;
        background: linear-gradient(90deg, #3b8ff8 0%, #7d53f8 100%);
        transition: width 0.3s ease;
      }
      .nav-link:hover::after {
        width: 100%;
      }
      .nav-link.active::after {
        width: 100%;
      }
    </style>
</head>
<body class="bg-gray-50 dark:bg-gray-900 transition-colors duration-300">
    <div id="app">
      <!-- Header -->
      <header class="bg-white dark:bg-gray-800 shadow-sm relative z-10">
        <div class="container mx-auto px-4 py-4 flex justify-between items-center">
          <div class="flex items-center">
            <div class="mr-4 p-2 bg-gradient-to-r from-blue-600 to-indigo-600 rounded-lg">
              <i data-feather="truck" class="text-white w-6 h-6"></i>
            </div>
            <h1 class="text-2xl font-bold primary-gradient-text">CheckList Pro</h1>
          </div>
          
          <div class="hidden md:flex space-x-8 items-center">
            <nav>
              <ul class="flex space-x-6">
                <li><a href="#home" class="nav-link active text-gray-900 dark:text-white">Home</a></li>
                <li><a href="#features" class="nav-link text-gray-600 dark:text-gray-400 hover:text-gray-900 dark:hover:text-white">Recursos</a></li>
                <li><a href="#how-it-works" class="nav-link text-gray-600 dark:text-gray-400 hover:text-gray-900 dark:hover:text-white">Como Funciona</a></li>
                <li><a href="#pricing" class="nav-link text-gray-600 dark:text-gray-400 hover:text-gray-900 dark:hover:text-white">Preços</a></li>
                <li><a href="#testimonials" class="nav-link text-gray-600 dark:text-gray-400 hover:text-gray-900 dark:hover:text-white">Depoimentos</a></li>
              </ul>
            </nav>
            <button id="dark-mode-toggle" class="p-2 rounded-lg bg-gray-100 dark:bg-gray-700">
              <i data-feather="moon" class="text-gray-800 dark:text-gray-200 w-5 h-5"></i>
            </button>
            <a href="#contact" class="px-4 py-2 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-medium hover:from-blue-700 hover:to-indigo-700 transition-all duration-300 transform hover:scale-105 shadow-lg">
              Experimente Grátis
            </a>
          </div>
          
          <button id="mobile-menu-button" class="md:hidden p-2 focus:outline-none">
            <i data-feather="menu" class="text-gray-800 dark:text-gray-200 w-6 h-6"></i>
          </button>
        </div>
        
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white dark:bg-gray-800 px-4 py-2 shadow-lg">
          <div class="container mx-auto">
            <ul class="space-y-2 py-4">
              <li><a href="#home" class="block px-4 py-2 text-gray-900 dark:text-white rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700">Home</a></li>
              <li><a href="#features" class="block px-4 py-2 text-gray-600 dark:text-gray-400 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700">Recursos</a></li>
              <li><a href="#how-it-works" class="block px-4 py-2 text-gray-600 dark:text-gray-400 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700">Como Funciona</a></li>
              <li><a href="#pricing" class="block px-4 py-2 text-gray-600 dark:text-gray-400 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700">Preços</a></li>
              <li><a href="#testimonials" class="block px-4 py-2 text-gray-600 dark:text-gray-400 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700">Depoimentos</a></li>
              <li>
                <a href="#contact" class="block px-4 py-2 text-center bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-medium my-2 hover:from-blue-700 hover:to-indigo-700 transition-all duration-300">
                  Experimente Grátis
                </a>
              </li>
              <li class="flex justify-center">
                <button id="mobile-dark-mode-toggle" class="p-2 rounded-lg bg-gray-100 dark:bg-gray-700">
                  <i data-feather="moon" class="text-gray-800 dark:text-gray-200 w-5 h-5"></i>
                </button>
              </li>
            </ul>
          </div>
        </div>
      </header>

      <!-- Hero Section -->
      <section id="home" class="relative py-20 overflow-hidden">
        <div id="vanta-bg"></div>
        <div class="container mx-auto px-4 relative z-10">
          <div class="flex flex-col lg:flex-row items-center">
            <div class="lg:w-1/2 mb-12 lg:mb-0" data-aos="fade-right">
              <h1 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-6 leading-tight">
                <span class="primary-gradient-text">Gestão Inteligente</span> de Frotas e CheckLists
              </h1>
              <p class="text-lg text-gray-600 dark:text-gray-300 mb-8 max-w-lg">
                A solução completa para gestão de transportes. Simplifique seus processos, aumente a segurança e reduza custos com nossa plataforma.
              </p>
              <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
                <a href="#contact" class="px-8 py-4 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-medium hover:from-blue-700 hover:to-indigo-700 transition-all duration-300 transform hover:scale-105 shadow-lg text-center">
                  Comece Agora
                </a>
                <a href="#features" class="px-8 py-4 bg-white dark:bg-gray-800 border border-gray-300 dark:border-gray-600 text-gray-900 dark:text-white rounded-lg font-medium hover:bg-gray-100 dark:hover:bg-gray-700 transition-all duration-300 transform hover:scale-105 text-center">
                  Saiba Mais
                </a>
              </div>
            </div>
            <div class="lg:w-1/2" data-aos="fade-left">
              <img src="http://static.photos/technology/1024x576/1" alt="Dashboard CheckList Pro" class="rounded-xl shadow-2xl border border-gray-200 dark:border-gray-700">
            </div>
          </div>
        </div>
      </section>

      <!-- Features Section -->
      <section id="features" class="py-20 bg-gray-50 dark:bg-gray-800">
        <div class="container mx-auto px-4">
          <div class="text-center mb-16" data-aos="fade-up">
            <h2 class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4">Recursos Poderosos</h2>
            <p class="text-lg text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
              Tudo que você precisa para gerenciar sua frota com eficiência e inteligência.
            </p>
          </div>
          
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="100">
              <div class="w-12 h-12 bg-blue-100 dark:bg-blue-900/50 rounded-lg flex items-center justify-center mb-4">
                <i data-feather="check-circle" class="text-blue-600 dark:text-blue-400 w-6 h-6"></i>
              </div>
              <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Checklist Digital</h3>
              <p class="text-gray-600 dark:text-gray-300">
                Realize inspeções veiculares de forma rápida e organizada com nosso checklist digital personalizável.
              </p>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="200">
              <div class="w-12 h-12 bg-purple-100 dark:bg-purple-900/50 rounded-lg flex items-center justify-center mb-4">
                <i data-feather="map-pin" class="text-purple-600 dark:text-purple-400 w-6 h-6"></i>
              </div>
              <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Monitoramento em Tempo Real</h3>
              <p class="text-gray-600 dark:text-gray-300">
                Acompanhe a localização e status de seus veículos em tempo real, com histórico de rotas.
              </p>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="300">
              <div class="w-12 h-12 bg-green-100 dark:bg-green-900/50 rounded-lg flex items-center justify-center mb-4">
                <i data-feather="bar-chart-2" class="text-green-600 dark:text-green-400 w-6 h-6"></i>
              </div>
              <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Relatórios Automatizados</h3>
              <p class="text-gray-600 dark:text-gray-300">
                Gere relatórios completos com dados de manutenção, consumo e produtividade da frota.
              </p>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="400">
              <div class="w-12 h-12 bg-yellow-100 dark:bg-yellow-900/50 rounded-lg flex items-center justify-center mb-4">
                <i data-feather="alert-triangle" class="text-yellow-600 dark:text-yellow-400 w-6 h-6"></i>
              </div>
              <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Alertas Inteligentes</h3>
              <p class="text-gray-600 dark:text-gray-300">
                Receba alertas sobre manutenções necessárias, documentos vencidos e prazos importantes.
              </p>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="500">
              <div class="w-12 h-12 bg-red-100 dark:bg-red-900/50 rounded-lg flex items-center justify-center mb-4">
                <i data-feather="shield" class="text-red-600 dark:text-red-400 w-6 h-6"></i>
              </div>
              <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Conformidade Legal</h3>
              <p class="text-gray-600 dark:text-gray-300">
                Garanta conformidade com as legislações de transporte e evite multas e penalidades.
              </p>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="600">
              <div class="w-12 h-12 bg-indigo-100 dark:bg-indigo-900/50 rounded-lg flex items-center justify-center mb-4">
                <i data-feather="smartphone" class="text-indigo-600 dark:text-indigo-400 w-6 h-6"></i>
              </div>
              <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Aplicativo Mobile</h3>
              <p class="text-gray-600 dark:text-gray-300">
                Acesso completo via aplicativo para motoristas e inspetores, mesmo offline.
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- How It Works Section -->
      <section id="how-it-works" class="py-20">
        <div class="container mx-auto px-4">
          <div class="text-center mb-16" data-aos="fade-up">
            <h2 class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4">Como Funciona</h2>
            <p class="text-lg text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
              Em poucos passos, você estará com sua frota digitalizada e sob controle total.
            </p>
          </div>
          
          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="relative" data-aos="fade-up" data-aos-delay="100">
              <div class="absolute -left-4 top-0 h-full w-0.5 bg-gray-200 dark:bg-gray-700 hidden md:block"></div>
              <div class="flex flex-col items-center md:items-start">
                <div class="w-16 h-16 bg-blue-100 dark:bg-blue-900/50 rounded-full flex items-center justify-center mb-4">
                  <span class="text-blue-600 dark:text-blue-400 font-bold text-xl">1</span>
                </div>
                <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2 text-center md:text-left">Cadastre sua Frota</h3>
                <p class="text-gray-600 dark:text-gray-300 text-center md:text-left">
                  Adicione todos os veículos e motoristas em nosso sistema de forma rápida e intuitiva.
                </p>
              </div>
            </div>
            
            <div class="relative" data-aos="fade-up" data-aos-delay="200">
              <div class="absolute -left-4 top-0 h-full w-0.5 bg-gray-200 dark:bg-gray-700 hidden md:block"></div>
              <div class="flex flex-col items-center md:items-start">
                <div class="w-16 h-16 bg-purple-100 dark:bg-purple-900/50 rounded-full flex items-center justify-center mb-4">
                  <span class="text-purple-600 dark:text-purple-400 font-bold text-xl">2</span>
                </div>
                <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2 text-center md:text-left">Personalize CheckLists</h3>
                <p class="text-gray-600 dark:text-gray-300 text-center md:text-left">
                  Crie modelos de checklist específicos para cada tipo de veículo e operação.
                </p>
              </div>
            </div>
            
            <div class="relative" data-aos="fade-up" data-aos-delay="300">
              <div class="flex flex-col items-center md:items-start">
                <div class="w-16 h-16 bg-green-100 dark:bg-green-900/50 rounded-full flex items-center justify-center mb-4">
                  <span class="text-green-600 dark:text-green-400 font-bold text-xl">3</span>
                </div>
                <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2 text-center md:text-left">Comece a Operar</h3>
                <p class="text-gray-600 dark:text-gray-300 text-center md:text-left">
                  Motoristas realizam checklists via app e gestores monitoram tudo online.
                </p>
              </div>
            </div>
          </div>
          
          <div class="mt-16 flex justify-center">
            <img src="http://static.photos/technology/1024x576/2" alt="Fluxo de trabalho CheckList Pro" class="rounded-xl shadow-lg border border-gray-200 dark:border-gray-700 w-full max-w-4xl" data-aos="zoom-in">
          </div>
        </div>
      </section>

      <!-- Pricing Section -->
      <section id="pricing" class="py-20 bg-gray-50 dark:bg-gray-800">
        <div class="container mx-auto px-4">
          <div class="text-center mb-16" data-aos="fade-up">
            <h2 class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4">Planos acessíveis</h2>
            <p class="text-lg text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
              Escolha o plano ideal para o tamanho da sua operação. Sem surpresas, sem compromisso.
            </p>
          </div>
          
          <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 max-w-5xl mx-auto">
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-blue-200 dark:border-blue-700/50" data-aos="fade-up" data-aos-delay="100">
              <div class="mb-6">
                <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-1">Básico</h3>
                <p class="text-gray-600 dark:text-gray-300">Ideal para pequenas frotas</p>
              </div>
              <div class="mb-6">
                <span class="text-5xl font-bold text-gray-900 dark:text-white">R$99</span>
                <span class="text-gray-600 dark:text-gray-300">/mês</span>
              </div>
              <ul class="space-y-3 mb-8">
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Até 10 veículos</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Checklists ilimitados</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">1 usuário administrador</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="x" class="text-gray-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-400">Monitoramento em tempo real</span>
                </li>
              </ul>
              <a href="#contact" class="block w-full px-6 py-3 bg-blue-600 hover:bg-blue-700 text-white rounded-lg font-medium text-center transition-colors duration-300">
                Assinar Plano
              </a>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-2xl hover:shadow-2xl transition-all duration-300 border-2 border-blue-400 dark:border-blue-600 transform scale-105 relative" data-aos="fade-up">
              <div class="absolute top-0 right-0 bg-blue-600 text-white text-xs font-semibold px-3 py-1 rounded-bl-lg rounded-tr-lg">
                RECOMENDADO
              </div>
              <div class="mb-6">
                <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-1">Profissional</h3>
                <p class="text-gray-600 dark:text-gray-300">Para frotas em crescimento</p>
              </div>
              <div class="mb-6">
                <span class="text-5xl font-bold text-gray-900 dark:text-white">R$249</span>
                <span class="text-gray-600 dark:text-gray-300">/mês</span>
              </div>
              <ul class="space-y-3 mb-8">
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Até 30 veículos</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Checklists ilimitados</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">3 usuários administradores</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Monitoramento em tempo real</span>
                </li>
              </ul>
              <a href="#contact" class="block w-full px-6 py-3 bg-gradient-to-r from-blue-600 to-indigo-600 hover:from-blue-700 hover:to-indigo-700 text-white rounded-lg font-medium text-center transition-all duration-300">
                Assinar Plano
              </a>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-blue-200 dark:border-blue-700/50" data-aos="fade-up" data-aos-delay="200">
              <div class="mb-6">
                <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-1">Empresarial</h3>
                <p class="text-gray-600 dark:text-gray-300">Para grandes operações</p>
              </div>
              <div class="mb-6">
                <span class="text-5xl font-bold text-gray-900 dark:text-white">R$499</span>
                <span class="text-gray-600 dark:text-gray-300">/mês</span>
              </div>
              <ul class="space-y-3 mb-8">
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Veículos ilimitados</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Checklists ilimitados</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Usuários ilimitados</span>
                </li>
                <li class="flex items-start">
                  <i data-feather="check" class="text-blue-600 dark:text-blue-400 w-5 h-5 mr-2"></i>
                  <span class="text-gray-600 dark:text-gray-300">Monitoramento em tempo real</span>
                </li>
              </ul>
              <a href="#contact" class="block w-full px-6 py-3 bg-blue-600 hover:bg-blue-700 text-white rounded-lg font-medium text-center transition-colors duration-300">
                Assinar Plano
              </a>
            </div>
          </div>
          
          <div class="mt-12 text-center text-gray-600 dark:text-gray-400" data-aos="fade-up">
            <p>Todos os planos incluem suporte 24/7 e atualizações gratuitas.</p>
            <p>Precisa de um plano personalizado? <a href="#contact" class="text-blue-600 dark:text-blue-400 hover:underline">Fale conosco</a></p>
          </div>
        </div>
      </section>

      <!-- Testimonials Section -->
      <section id="testimonials" class="py-20">
        <div class="container mx-auto px-4">
          <div class="text-center mb-16" data-aos="fade-up">
            <h2 class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4">Quem usa recomenda</h2>
            <p class="text-lg text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
              Veja o que nossos clientes dizem sobre a plataforma CheckList Pro.
            </p>
          </div>
          
          <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="100">
              <div class="flex items-center gap-4 mb-4">
                <img src="http://static.photos/people/200x200/1" alt="João Silva" class="w-12 h-12 rounded-full">
                <div>
                  <h4 class="font-semibold text-gray-900 dark:text-white">João Silva</h4>
                  <p class="text-sm text-gray-600 dark:text-gray-400">Transportadora JS Logística</p>
                </div>
              </div>
              <p class="text-gray-600 dark:text-gray-300 italic mb-4">
                "O CheckList Pro transformou nossa operação. Reduzimos em 60% os problemas mecânicos nos veículos e tudo ficou muito mais organizado."
              </p>
              <div class="flex text-yellow-400">
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
              </div>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="200">
              <div class="flex items-center gap-4 mb-4">
                <img src="http://static.photos/people/200x200/2" alt="Maria Santos" class="w-12 h-12 rounded-full">
                <div>
                  <h4 class="font-semibold text-gray-900 dark:text-white">Maria Santos</h4>
                  <p class="text-sm text-gray-600 dark:text-gray-400">Frota Empresarial</p>
                </div>
              </div>
              <p class="text-gray-600 dark:text-gray-300 italic mb-4">
                "A facilidade para criar checklists específicos nos ajudou muito. Agora temos padrões diferentes para cada tipo de veículo e operação."
              </p>
              <div class="flex text-yellow-400">
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
              </div>
            </div>
            
            <div class="bg-white dark:bg-gray-700 rounded-xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-200 dark:border-gray-600" data-aos="fade-up" data-aos-delay="300">
              <div class="flex items-center gap-4 mb-4">
                <img src="http://static.photos/people/200x200/3" alt="Carlos Oliveira" class="w-12 h-12 rounded-full">
                <div>
                  <h4 class="font-semibold text-gray-900 dark:text-white">Carlos Oliveira</h4>
                  <p class="text-sm text-gray-600 dark:text-gray-400">Carga Pesada Express</p>
                </div>
              </div>
              <p class="text-gray-600 dark:text-gray-300 italic mb-4">
                "Os motoristas adoraram o aplicativo simples e intuitivo. A redução de papéis e a organização dos checklists foram fundamentais para nosso crescimento."
              </p>
              <div class="flex text-yellow-400">
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4 fill-current"></i>
                <i data-feather="star" class="w-4 h-4"></i>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- CTA Section -->
      <section id="contact" class="py-20 bg-gradient-to-r from-blue-600 to-indigo-600 text-white">
        <div class="container mx-auto px-4">
          <div class="max-w-3xl mx-auto text-center" data-aos="fade-up">
            <h2 class="text-3xl md:text-4xl font-bold mb-6">Pronto para otimizar sua frota?</h2>
            <p class="text-xl opacity-90 mb-8">
              Experimente gratuitamente por 14 dias e descubra como podemos transformar sua gestão de transportes.
            </p>
            <div class="flex flex-col sm:flex-row gap-4 justify-center">
              <a href="#" class="px-8 py-4 bg-white text-blue-600 rounded-lg font-bold hover:bg-gray-100 transition-all duration-300 transform hover:scale-105 shadow-lg">
                Comece Agora Gratuitamente
              </a>
              <a href="#" class="px-8 py-4 border-2 border-white text-white rounded-lg font-bold hover:bg-white/10 transition-all duration-300">
                Fale com um especialista
              </a>
            </div>
          </div>
        </div>
      </section>

      <!-- Footer -->
      <footer class="bg-gray-900 text-gray-300 py-12">
        <div class="container mx-auto px-4">
          <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
            <div>
              <h3 class="text-xl font-bold text-white mb-4 flex items-center">
                <div class="mr-2 p-1 bg-gradient-to-r from-blue-600 to-indigo-600 rounded-lg">
                  <i data-feather="truck" class="text-white w-5 h-5"></i>
                </div>
                CheckList Pro
              </h3>
              <p class="mb-4">
                A solução completa para gestão de frotas e checklists veiculares.
              </p>
              <div class="flex space-x-4">
                <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
                  <i data-feather="facebook" class="w-5 h-5"></i>
                </a>
                <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
                  <i data-feather="twitter" class="w-5 h-5"></i>
                </a>
                <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
                  <i data-feather="linkedin" class="w-5 h-5"></i>
                </a>
                <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
                  <i data-feather="instagram" class="w-5 h-5"></i>
                </a>
              </div>
            </div>
            
            <div>
              <h4 class="text-lg font-semibold text-white mb-4">Produto</h4>
              <ul class="space-y-2">
                <li><a href="#" class="hover:text-white transition-colors duration-300">Recursos</a></li>
                <li><a href="#" class="hover:text-white transition-colors duration-300">Preços</a></li>
                <li><a href="#" class="hover:text-white transition-colors duration-300">Aplicativo</a></li>
                <li><a href="#" class="hover:text-white transition-colors duration-300">Integrações</a></li>
              </ul>
            </div>
            
            <div>
              <h4 class="text-lg font-semibold text-white mb-4">Sobre</h4>
              <ul class="space-y-2">
                <li><a href="#" class="hover:text-white transition-colors duration-300">Nossa História</a></li>
                <li><a href="#" class="hover:text-white transition-colors duration-300">Carreiras</a></li>
                <li><a href="#" class="hover:text-white transition-colors duration-300">Blog</a></li>
                <li><a href="#" class="hover:text-white transition-colors duration-300">Parceiros</a></li>
              </ul>
            </div>
            
            <div>
              <h4 class="text-lg font-semibold text-white mb-4">Contato</h4>
              <ul class="space-y-2">
                <li class="flex items-center gap-2">
                  <i data-feather="mail" class="w-4 h-4"></i>
                  <a href="mailto:contato@checklistpro.com.br" class="hover:text-white transition-colors duration-300">contato@checklistpro.com.br</a>
                </li>
                <li class="flex items-center gap-2">
                  <i data-feather="phone" class="w-4 h-4"></i>
                  <a href="tel:+5511999999999" class="hover:text-white transition-colors duration-300">+55 11 99999-9999</a>
                </li>
                <li class="flex items-center gap-2">
                  <i data-feather="map-pin" class="w-4 h-4"></i>
                  <span>São Paulo - SP, Brasil</span>
                </li>
              </ul>
            </div>
          </div>
          
          <div class="border-t border-gray-800 mt-12 pt-8 text-sm text-gray-500 text-center">
            <p>&copy; 2024 CheckList Pro. Todos os direitos reservados.</p>
          </div>
        </div>
      </footer>
    </div>

    <script>
      // Initialize animations
      AOS.init({
        duration: 800,
        easing: 'ease-in-out',
        once: true
      });
      
      // Initialize feather icons
      feather.replace();
      
      // Dark mode toggle
      const darkModeToggle = document.getElementById('dark-mode-toggle');
      const mobileDarkModeToggle = document.getElementById('mobile-dark-mode-toggle');
      
      if (localStorage.getItem('darkMode') === 'true') {
        document.documentElement.classList.add('dark');
        darkModeToggle.innerHTML = feather.icons.sun.toSvg({ class: 'text-yellow-400 w-5 h-5' });
        mobileDarkModeToggle.innerHTML = feather.icons.sun.toSvg({ class: 'text-yellow-400 w-5 h-5' });
      } else {
        document.documentElement.classList.remove('dark');
        darkModeToggle.innerHTML = feather.icons.moon.toSvg({ class: 'text-gray-800 dark:text-gray-200 w-5 h-5' });
        mobileDarkModeToggle.innerHTML = feather.icons.moon.toSvg({ class: 'text-gray-800 dark:text-gray-200 w-5 h-5' });
      }
      
      darkModeToggle.addEventListener('click', () => {
        document.documentElement.classList.toggle('dark');
        if (document.documentElement.classList.contains('dark')) {
          localStorage.setItem('darkMode', 'true');
          darkModeToggle.innerHTML = feather.icons.sun.toSvg({ class: 'text-yellow-400 w-5 h-5' });
          mobileDarkModeToggle.innerHTML = feather.icons.sun.toSvg({ class: 'text-yellow-400 w-5 h-5' });
        } else {
          localStorage.setItem('darkMode', 'false');
          darkModeToggle.innerHTML = feather.icons.moon.toSvg({ class: 'text-gray-800 dark:text-gray-200 w-5 h-5' });
          mobileDarkModeToggle.innerHTML = feather.icons.moon.toSvg({ class: 'text-gray-800 dark:text-gray-200 w-5 h-5' });
        }
      });
      
      mobileDarkModeToggle.addEventListener('click', () => {
        document.documentElement.classList.toggle('dark');
        if (document.documentElement.classList.contains('dark')) {
          localStorage.setItem('darkMode', 'true');
          darkModeToggle.innerHTML = feather.icons.sun.toSvg({ class: 'text-yellow-400 w-5 h-5' });
          mobileDarkModeToggle.innerHTML = feather.icons.sun.toSvg({ class: 'text-yellow-400 w-5 h-5' });
        } else {
          localStorage.setItem('darkMode', 'false');
          darkModeToggle.innerHTML = feather.icons.moon.toSvg({ class: 'text-gray-800 dark:text-gray-200 w-5 h-5' });
          mobileDarkModeToggle.innerHTML = feather.icons.moon.toSvg({ class: 'text-gray-800 dark:text-gray-200 w-5 h-5' });
        }
      });
      
      // Mobile menu toggle
      const mobileMenuButton = document.getElementById('mobile-menu-button');
      const mobileMenu = document.getElementById('mobile-menu');
      
      mobileMenuButton.addEventListener('click', () => {
        mobileMenu.classList.toggle('hidden');
      });
      
      // Close mobile menu when clicking on a link
      const mobileLinks = document.querySelectorAll('#mobile-menu a');
      mobileLinks.forEach(link => {
        link.addEventListener('click', () => {
          mobileMenu.classList.add('hidden');
        });
      });
      
      // Smooth scrolling for anchor links
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
          e.preventDefault();
          
          const target = document.querySelector(this.getAttribute('href'));
          if (target) {
            window.scrollTo({
              top: target.offsetTop - 80,
              behavior: 'smooth'
            });
          }
        });
      });
      
      // Set active nav link based on scroll position
      const sections = document.querySelectorAll('section');
      const navLinks = document.querySelectorAll('.nav-link');
      
      window.addEventListener('scroll', () => {
        let current = '';
        
        sections.forEach(section => {
          const sectionTop = section.offsetTop;
          const sectionHeight = section.clientHeight;
          
          if (pageYOffset >= (sectionTop - sectionHeight / 3)) {
            current = section.getAttribute('id');
          }
        });
        
        navLinks.forEach(link => {
          link.classList.remove('active');
          link.classList.remove('text-gray-900', 'dark:text-white');
          link.classList.add('text-gray-600', 'dark:text-gray-400');
          
          if (link.getAttribute('href') === `#${current}`) {
            link.classList.add('active');
            link.classList.add('text-gray-900', 'dark:text-white');
            link.classList.remove('text-gray-600', 'dark:text-gray-400');
          }
        });
      });
      
      // Vanta.js background effect
      VANTA.GLOBE({
        el: "#vanta-bg",
        mouseControls: true,
        touchControls: true,
        gyroControls: false,
        minHeight: 200.00,
        minWidth: 200.00,
        scale: 1.00,
        scaleMobile: 1.00,
        color: 0x3b82f6,
        backgroundColor: 0xffffff,
        size: 0.8
      });
    </script>
</body>
</html>
