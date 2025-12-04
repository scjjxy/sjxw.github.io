<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>从“钢铁洪流”到“智胜未来” - 中国国防现代化十年跃迁</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#0f3460',
                        secondary: '#1a508b',
                        accent: '#e94560',
                        dark: '#0a1929',
                        light: '#f5f9ff'
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                        serif: ['Merriweather', 'Georgia', 'serif']
                    },
                }
            }
        }
    </script>
    <style type="text/tailwindcss">
        @layer utilities {
            .text-shadow {
                text-shadow: 0 2px 4px rgba(0,0,0,0.1);
            }
            .text-shadow-lg {
                text-shadow: 0 4px 8px rgba(0,0,0,0.3);
            }
            .scrollbar-hide::-webkit-scrollbar {
                display: none;
            }
            .scrollbar-hide {
                -ms-overflow-style: none;
                scrollbar-width: none;
            }
            .animate-fade-in {
                animation: fadeIn 0.8s ease-in-out;
            }
            .animate-slide-up {
                animation: slideUp 0.8s ease-out;
            }
            .animate-pulse-slow {
                animation: pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite;
            }
            .text-indent-2 {
                text-indent: 2em;
            }
            .image-overlay {
                position: absolute;
                top: 0;
                left: 0;
                right: 0;
                bottom: 0;
                background: linear-gradient(to bottom, rgba(15, 52, 96, 0.7), rgba(10, 25, 41, 0.9));
            }
            .hover-scale {
                transition: transform 0.3s ease;
            }
            .hover-scale:hover {
                transform: scale(1.03);
            }
            .scroll-indicator {
                height: 3px;
                background-color: #e94560;
                position: fixed;
                top: 0;
                left: 0;
                z-index: 9999;
                width: 0%;
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from { transform: translateY(30px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .chart-container {
            position: relative;
            height: 350px;
            width: 100%;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -24px;
            top: 8px;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: #0f3460;
            border: 2px solid #fff;
            box-shadow: 0 0 0 2px #0f3460;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: -18px;
            top: 0;
            bottom: 0;
            width: 2px;
            background-color: #e2e8f0;
        }

        .nav-link.active {
            border-left: 3px solid #e94560;
            color: #e94560;
            font-weight: 600;
        }

        .card-hover {
            transition: all 0.3s ease;
        }

        .card-hover:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        /* 装饰性元素 */
        .decorative-pattern {
            background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%230f3460' fill-opacity='0.05'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
        }
        
        .badge {
            position: absolute;
            top: -10px;
            right: -10px;
            background-color: #e94560;
            color: white;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }
    </style>
</head>
<body class="bg-gray-50 font-sans text-gray-800 decorative             decorative-pattern">
    <!-- 滚动进度指示器 -->
    <div class="scroll-indicator" id="scrollIndicator"></div>
    
    <!-- 顶部导航栏 -->
    <header class="fixed top-0 left-0 right-0 bg-primary/95 text-white z-50 transition-all duration-300" id="navbar">
        <div class="container mx-auto px-4 py-3 flex justify-between items-center">
            <h1 class="text-xl md:text-2xl font-bold flex items-center">
                <i class="fa fa-line-chart mr-2 text-accent"></i>
                <span>数据新闻</span>
            </h1>
            <nav class="hidden md:block">
                <ul class="flex space-x-6">
                    <li><a href="#intro" class="hover:text-accent transition-colors">引言</a></li>
                    <li><a href="#equipment" class="hover:text-accent transition-colors">装备更新</a></li>
                    <li><a href="#services" class="hover:text-accent transition-colors">军种结构</a></li>
                    <li><a href="#drones" class="hover:text-accent transition-colors">无人方阵</a></li>
                    <li><a href="#missiles" class="hover:text-accent transition-colors">大国长剑</a></li>
                    <li><a href="#conclusion" class="hover:text-accent transition-colors">结论</a></li>
                </ul>
            </nav>
            <button class="md:hidden text-white focus:outline-none" id="menu-toggle">
                <i class="fa fa-bars text-xl"></i>
            </button>
        </div>
        <!-- 移动端菜单 -->
        <div class="md:hidden bg-secondary hidden" id="mobile-menu">
            <ul class="container mx-auto px-4 py-2 space-y-3">
                <li><a href="#intro" class="block py-2 hover:text-accent transition-colors">引言</a></li>
                <li><a href="#equipment" class="block py-2 hover:text-accent transition-colors">装备更新</a></li>
                <li><a href="#services" class="block py-2 hover:text-accent transition-colors">军种结构</a></li>
                <li><a href="#drones" class="block py-2 hover:text-accent transition-colors">无人方阵</a></li>
                <li><a href="#missiles" class="block py-2 hover:text-accent transition-colors">大国长剑</a></li>
                <li><a href="#conclusion" class="block py-2 hover:text-accent transition-colors">结论</a></li>
            </ul>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section class="relative pt-32 pb-20 bg-gradient-to-b from-primary to-dark text-white overflow-hidden">
        <div class="absolute inset-0 opacity-20">
            <img src="https://picsum.photos/id/1041/1920/1080" alt="军事背景" class="w-full h-full object-cover">
        </div>
        <div class="image-overlay"></div>
        <div class="container mx-auto px-4 relative z-10">
            <div class="max-w-4xl mx-auto text-center animate-fade-in">
                <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6 text-shadow-lg">从“钢铁洪流”到“智胜未来”</h1>
                <p class="text-xl md:text-2xl text-gray-200 mb-8">九三阅兵透视中国国防现代化十年跃迁</p>
                <div class="flex flex-wrap justify-center gap-4">
                    <a href="#intro" class="bg-accent hover:bg-accent/90 text-white font-medium py-3 px-6 rounded-lg transition-all duration-300 flex items-center group">
                        <i class="fa fa-book mr-2 group-hover:rotate-6 transition-transform"></i> 开始阅读
                    </a>
                    <a href="#equipment" class="bg-transparent border-2 border-white hover:bg-white/10 text-white font-medium py-3 px-6 rounded-lg transition-all duration-300 flex items-center group">
                        <i class="fa fa-bar-chart mr-2 group-hover:scale-110 transition-transform"></i> 查看数据
                    </a>
                </div>
                
                <!-- 装饰性时间轴标记 -->
                <div class="flex justify-center mt-12 space-x-8">
                    <div class="flex flex-col items-center">
                        <div class="w-12 h-12 rounded-full bg-white/10 flex items-center justify-center mb-2">
                            <span class="font-bold">2015</span>
                        </div>
                        <span class="text-sm text-gray-300">抗战胜利70周年</span>
                    </div>
                    <div class="h-1 w-8 bg-white/30 self-center"></div>
                    <div class="flex flex-col items-center">
                        <div class="w-12 h-12 rounded-full bg-white/10 flex items-center justify-center mb-2">
                            <span class="font-bold">2019</span>
                        </div>
                        <span class="text-sm text-gray-300">新中国成立70周年</span>
                    </div>
                    <div class="h-1 w-8 bg-white/30 self-center"></div>
                    <div class="flex flex-col items-center">
                        <div class="w-12 h-12 rounded-full bg-accent/80 flex items-center justify-center mb-2">
                            <span class="font-bold">2025</span>
                        </div>
                        <span class="text-sm text-gray-300">抗战胜利80周年</span>
                    </div>
                </div>
            </div>
        </div>
        <div class="absolute bottom-0 left-0 right-0 h-16 bg-gradient-to-t from-gray-50 to-transparent"></div>
    </section>

    <!-- 主内容区域 -->
    <main class="container mx-auto px-4 py-12">
        <!-- 引言部分 -->
        <section id="intro" class="max-w-5xl mx-auto mb-20 animate-slide-up">
            <div class="bg-white rounded-xl shadow-xl p-8 md:p-10 relative overflow-hidden">
                <!-- 装饰性元素 -->
                <div class="absolute -right-10 -top-10 w-40 h-40 bg-primary/5 rounded-full"></div>
                <div class="absolute -left-16 -bottom-16 w-40 h-40 bg-accent/5 rounded-full"></div>
                
                <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4 relative z-10">引言：一场阅兵，十年之变</h2>
                
                <div class="flex flex-col md:flex-row gap-8 items-center mb-6">
                    <div class="w-full md:w-1/2">
                        <div class="rounded-lg overflow-hidden shadow-md hover-scale">
                            <img src="images/1.jpg" alt="阅兵仪式" class="w-full h-auto">
                            <div class="bg-gray-100 px-4 py-2 text-sm text-gray-600">
                                2025年9月3日，北京天安门广场阅兵仪式现场
                            </div>
                        </div>
                    </div>
                    
                    <div class="w-full md:w-1/2 prose prose-lg max-w-none relative z-10">
                        <p class="mb-4 text-indent-2">2025年9月3日上午，北京天安门广场，伴随着《义勇军进行曲》的雄壮旋律，纪念中国人民抗日战争暨世界反法西斯战争胜利80周年的盛大阅兵拉开帷幕。当由数十架高空高速无人机组成的“无人作战第2方队”以编队形式低空掠过长安街，当东风-41洲际战略核导弹在重型运输车上缓缓驶来，全球军事观察家的目光再次聚焦中国。</p>
                        <p class="mb-4 text-indent-2">公众的直观感受往往是“震撼”“自豪”，但在这情绪背后，一个更值得追问的问题是：过去十年，中国军队究竟发生了哪些结构性、技术性、战略性的跃迁？这些变化是否足以支撑“世界一流军队”的目标？</p>
                        <p class="text-indent-2">本文通过系统梳理2015年、2019年与2025年三次重大阅兵中的装备数据、军种构成与展示逻辑，揭示中国国防现代化的真实图景。</p>
                    </div>
                </div>
                
                <!-- 关键数据亮点卡片 -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mt-8 relative z-10">
                    <div class="bg-primary/5 p-4 rounded-lg border border-primary/10">
                        <div class="flex items-center mb-2">
                            <i class="fa fa-rocket text-primary mr-2"></i>
                            <h4 class="font-semibold">装备更新率</h4>
                        </div>
                        <p class="text-3xl font-bold text-accent">62%</p>
                        <p class="text-sm text-gray-600">2025年新装备占比，较2015年提升32%</p>
                    </div>
                    <div class="bg-primary/5 p-4 rounded-lg border border-primary/10">
                        <div class="flex items-center mb-2">
                            <i class="fa fa-users text-primary mr-2"></i>
                            <h4 class="font-semibold">军种结构</h4>
                        </div>
                        <p class="text-3xl font-bold text-accent">32%</p>
                        <p class="text-sm text-gray-600">陆军占比，较2015年下降26%</p>
                    </div>
                    <div class="bg-primary/5 p-4 rounded-lg border border-primary/10">
                        <div class="flex items-center mb-2">
                            <i class="fa fa-plane text-primary mr-2"></i>
                            <h4 class="font-semibold">无人装备</h4>
                        </div>
                        <p class="text-3xl font-bold text-accent">3×</p>
                        <p class="text-sm text-gray-600">2025年无人装备方队数量较2019年翻倍</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 装备更新加速 -->
        <section id="equipment" class="max-w-5xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden card-hover">
                <div class="p-8 md:p-10">
                    <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">一、装备更新加速：新质战斗力成主角</h2>
                    <h3 class="text-xl font-semibold mb-4 text-secondary">从“换代”到“代差”：装备迭代进入快车道</h3>
                    
                    <div class="flex flex-col lg:flex-row gap-8 mb-8">
                        <div class="w-full lg:w-1/2 prose prose-lg max-w-none">
                            <p class="mb-4 text-indent-2">2015年阅兵时，中国首次集中展示国产主战装备，如99A主战坦克、歼-15舰载机、东风-21D反舰弹道导弹等，标志着“自主可控”能力初步形成。然而，当时仍有近七成装备为改进型或延续型号。</p>
                            <p class="text-indent-2">而到了2025年，情况已截然不同。值得注意的是，2025年的新装备中，高超音速武器、隐身无人机、智能弹药、电磁炮试验平台、量子通信终端等前沿技术装备首次公开亮相，且多具备“改变游戏规则”（game-changing）的潜力。</p>
                            
                            <div class="bg-blue-50 border-l-4 border-primary p-4 rounded-r-lg mt-6">
                                <p class="italic text-gray-700">国防大学教授李明指出：“过去我们追赶的是‘有没有’，现在追求的是‘好不好’‘快不快’‘能不能打智能仗’。2025年阅兵展示的不是单一武器，而是一个完整的智能作战生态。”</p>
                            </div>
                        </div>
                        
                        <div class="w-full lg:w-1/2">
                            <div class="chart-container mb-6">
                                <canvas id="equipmentChart"></canvas>
                            </div>
                            
                            <!-- 装备对比卡片 -->
                            <div class="bg-gray-50 rounded-lg p-4 border border-gray-100">
                                <h4 class="font-semibold text-primary mb-3 flex items-center">
                                    <i class="fa fa-exchange mr-2"></i> 装备代际对比
                                </h4>
                                <div class="grid grid-cols-2 gap-4 text-sm">
                                    <div class="bg-white p-3 rounded shadow-sm">
                                        <p class="text-gray-500">2015年主力装备</p>
                                        <p class="font-medium">99A主战坦克</p>
                                        <p class="font-medium">歼-15舰载机</p>
                                        <p class="font-medium">东风-21D反舰导弹</p>
                                    </div>
                                    <div class="bg-white p-3 rounded shadow-sm">
                                        <p class="text-gray-500">2025年主力装备</p>
                                        <p class="font-medium text-accent">15式轻型坦克</p>
                                        <p class="font-medium text-accent">歼-35隐身舰载机</p>
                                        <p class="font-medium text-accent">东风-17高超音速导弹</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- 装备图片展示 -->
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mt-8">
                        <div class="relative rounded-lg overflow-hidden shadow-md group">
                            <img src="images/2.1.png" alt="新型坦克" class="w-full h-48 object-cover transition-transform duration-500 group-hover:scale-110">
                            <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity flex items-end">
                                <p class="text-white p-3 text-sm">15式轻型坦克 - 适应全域作战环境</p>
                            </div>
                        </div>
                        <div class="relative rounded-lg overflow-hidden shadow-md group">
                            <img src="images/2.2.jpg" alt="隐身战机" class="w-full h-48 object-cover transition-transform duration-500 group-hover:scale-110">
                            <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity flex items-end">
                                <p class="text-white p-3 text-sm">歼-35隐身舰载机 - 航母编队核心战力</p>
                            </div>
                        </div>
                        <div class="relative rounded-lg overflow-hidden shadow-md group">
                            <img src="images/2.3.jpg" alt="高超音速导弹" class="w-full h-48 object-cover transition-transform duration-500 group-hover:scale-110">
                            <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity flex items-end">
                                <p class="text-white p-3 text-sm">东风-17 - 难以拦截的高超音速武器</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 军种结构重塑 -->
        <section id="services" class="max-w-5xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden card-hover">
                <div class="p-8 md:p-10">
                    <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">二、军种结构重塑：从陆军主导到多维联合作战</h2>
                    <h3 class="text-xl font-semibold mb-4 text-secondary">“大陆军主义”的终结与联合作战体制的确立</h3>
                    
                    <div class="prose prose-lg max-w-none mb-8">
                        <p class="mb-4 text-indent-2">长期以来，中国人民解放军以陆军为核心，2015年改革前，陆军占全军总员额近60%。但随着“军委管总、战区主战、军种主建”改革推进，军队结构发生根本性转变。</p>
                        <p class="text-indent-2">这一变化清晰反映了中国军队从“平面陆军”向“立体联合作战”转型的战略意图。尤其值得关注的是，战略支援部队在2025年阅兵中不仅独立成方，还展示了天基侦察、网络攻防、电子对抗、心理战等多维能力，标志着“制信息权”已成为现代战争的核心制高点。</p>
                    </div>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
                        <div class="chart-container">
                            <canvas id="servicesChart"></canvas>
                        </div>
                        <div class="bg-gray-50 rounded-lg p-6">
                            <h4 class="font-semibold text-lg mb-4 text-primary flex items-center">
                                <i class="fa fa-table mr-2"></i>军种结构变化数据表
                            </h4>
                            <div class="overflow-x-auto">
                                <table class="min-w-full divide-y divide-gray-200">
                                    <thead>
                                        <tr>
                                            <th class="px-4 py-3 bg-gray-100 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">军种/部队</th>
                                            <th class="px-4 py-3 bg-gray-100 text-center text-xs font-medium text-gray-500 uppercase tracking-wider">2015年</th>
                                            <th class="px-4 py-3 bg-gray-100 text-center text-xs font-medium text-gray-500 uppercase tracking-wider">2019年</th>
                                            <th class="px-4 py-3 bg-gray-100 text-center text-xs font-medium text-gray-500 uppercase tracking-wider">2025年</th>
                                        </tr>
                                    </thead>
                                    <tbody class="bg-white divide-y divide-gray-200">
                                        <tr>
                                            <td class="px-4 py-3 text-sm font-medium">陆军</td>
                                            <td class="px-4 py-3 text-sm text-center">58%</td>
                                            <td class="px-4 py-3 text-sm text-center">45%</td>
                                            <td class="px-4 py-3 text-sm text-center font-semibold text-accent">32%</td>
                                        </tr>
                                        <tr>
                                            <td class="px-4 py-3 text-sm font-medium">海军</td>
                                            <td class="px-4 py-3 text-sm text-center">12%</td>
                                            <td class="px-4 py-3 text-sm text-center">15%</td>
                                            <td class="px-4 py-3 text-sm text-center font-semibold text-primary">18%</td>
                                        </tr>
                                        <tr>
                                            <td class="px-4 py-3 text-sm font-medium">空军</td>
                                            <td class="px-4 py-3 text-sm text-center">10%</td>
                                            <td class="px-4 py-3 text-sm text-center">14%</td>
                                            <td class="px-4 py-3 text-sm text-center font-semibold text-primary">16%</td>
                                        </tr>
                                        <tr>
                                            <td class="px-4 py-3 text-sm font-medium">火箭军</td>
                                            <td class="px-4 py-3 text-sm text-center">8%</td>
                                            <td class="px-4 py-3 text-sm text-center">12%</td>
                                            <td class="px-4 py-3 text-sm text-center font-semibold text-primary">14%</td>
                                        </tr>
                                        <tr>
                                            <td class="px-4 py-3 text-sm font-medium">战略支援部队</td>
                                            <td class="px-4 py-3 text-sm text-center">0%</td>
                                            <td class="px-4 py-3 text-sm text-center">8%</td>
                                            <td class="px-4 py-3 text-sm text-center font-semibold text-primary">12%</td>
                                        </tr>
                                        <tr>
                                            <td class="px-4 py-3 text-sm font-medium">联勤保障/其他</td>
                                            <td class="px-4 py-3 text-sm text-center">12%</td>
                                            <td class="px-4 py-3 text-sm text-center">6%</td>
                                            <td class="px-4 py-3 text-sm text-center">8%</td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                            <p class="text-xs text-gray-500 mt-3 italic text-center">数据来源：国防部官网方队介绍、IISS《Military Balance 2025》交叉验证</p>
                        </div>
                    </div>
                    
                    <!-- 军种图标与说明 -->
                    <div class="grid grid-cols-2 md:grid-cols-5 gap-4 mt-8">
                        <div class="bg-primary/5 rounded-lg p-4 text-center hover:bg-primary/10 transition-colors">
                            <div class="w-12 h-12 bg-primary/10 rounded-full flex items-center justify-center mx-auto mb-2">
                                <i class="fa fa-shield text-primary text-xl"></i>
                            </div>
                            <h5 class="font-medium text-sm">陆军</h5>
                            <p class="text-xs text-gray-500 mt-1">全域机动能力提升</p>
                        </div>
                        <div class="bg-primary/5 rounded-lg p-4 text-center hover:bg-primary/10 transition-colors">
                            <div class="w-12 h-12 bg-primary/10 rounded-full flex items-center justify-center mx-auto mb-2">
                                <i class="fa fa-ship text-primary text-xl"></i>
                            </div>
                            <h5 class="font-medium text-sm">海军</h5>
                            <p class="text-xs text-gray-500 mt-1">远洋作战能力形成</p>
                        </div>
                        <div class="bg-primary/5 rounded-lg p-4 text-center hover:bg-primary/10 transition-colors">
                            <div class="w-12 h-12 bg-primary/10 rounded-full flex items-center justify-center mx-auto mb-2">
                                <i class="fa fa-plane text-primary text-xl"></i>
                            </div>
                            <h5 class="font-medium text-sm">空军</h5>
                            <p class="text-xs text-gray-500 mt-1">战略投送能力增强</p>
                        </div>
                        <div class="bg-primary/5 rounded-lg p-4 text-center hover:bg-primary/10 transition-colors">
                            <div class="w-12 h-12 bg-primary/10 rounded-full flex items-center justify-center mx-auto mb-2">
                                <i class="fa fa-rocket text-primary text-xl"></i>
                            </div>
                            <h5 class="font-medium text-sm">火箭军</h5>
                            <p class="text-xs text-gray-500 mt-1">核常兼备威慑力提升</p>
                        </div>
                        <div class="bg-primary/5 rounded-lg p-4 text-center hover:bg-primary/10 transition-colors">
                            <div class="w-12 h-12 bg-primary/10 rounded-full flex items-center justify-center mx-auto mb-2">
                                <i class="fa fa-satellite text-primary text-xl"></i>
                            </div>
                            <h5 class="font-medium text-sm">战略支援部队</h5>
                            <p class="text-xs text-gray-500 mt-1">信息主导权争夺核心</p>
                        </div>
                    </div>
                    
                    <p class="text-gray-700 mt-6">相比之下，美国2023年“国庆日”阅兵（虽规模较小）中，网络司令部与太空军已占据显著位置。中国的调整虽起步稍晚，但步伐更为紧凑。</p>
                </div>
            </div>
        </section>

        <!-- 无人方阵进化史 -->
        <section id="drones" class="max-w-5xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden card-hover">
                <div class="p-8 md:p-10">
                    <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">三、“无人方阵”进化史：从配角到体系化作战核心</h2>
                    <h3 class="text-xl font-semibold mb-4 text-secondary">无人系统的“三级跳”</h3>
                    
                    <div class="prose prose-lg max-w-none mb-8">
                        <p class="mb-4 text-indent-2">2015年，BZK-005侦察无人机仅作为陆军方队的附属装备出现，功能单一；2019年，攻击-11隐身无人攻击机惊艳亮相，具备内埋弹舱与飞翼布局，可执行穿透性打击任务；而2025年，三个完整的无人作战方队依次登场，涵盖侦察感知层、精确打击层和集群协同层。</p>
                    </div>
                    
                    <div class="relative timeline pl-8 mb-10 py-4">
                        <div class="timeline-item relative mb-10">
                            <div class="absolute -left-32 top-0 bg-primary text-white text-xs font-bold px-3 py-1 rounded-full">
                                2015
                            </div>
                            <h4 class="text-lg font-semibold text-primary mb-2">侦察为主，附属装备</h4>
                            <div class="bg-gray-50 p-4 rounded-lg shadow-sm hover-scale">
                                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                    <div>
                                        <span class="text-sm text-gray-500">装备名称</span>
                                        <p class="font-medium">BZK-005</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">类型</span>
                                        <p>高空长航时侦察无人机</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">所属方队</span>
                                        <p>陆军航空兵方队（附属）</p>
                                    </div>
                                </div>
                                <p class="mt-3 text-sm">
                                    <span class="text-gray-500">主要特点：</span>
                                    最大升限8000米，续航20小时，首次公开
                                </p>
                            </div>
                        </div>
                        
                        <div class="timeline-item relative mb-10">
                            <div class="absolute -left-32 top-0 bg-primary text-white text-xs font-bold px-3 py-1 rounded-full">
                                2019
                            </div>
                            <h4 class="text-lg font-semibold text-primary mb-2">隐身攻击，独立成方</h4>
                            <div class="bg-gray-50 p-4 rounded-lg shadow-sm mb-4 hover-scale">
                                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                    <div>
                                        <span class="text-sm text-gray-500">装备名称</span>
                                        <p class="font-medium">攻击-11</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">类型</span>
                                        <p>隐身无人攻击机</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">所属方队</span>
                                        <p>无人作战第1方队（独立）</p>
                                    </div>
                                </div>
                                <p class="mt-3 text-sm">
                                    <span class="text-gray-500">主要特点：</span>
                                    飞翼布局，内埋弹舱，具备穿透打击能力
                                </p>
                            </div>
                            <div class="bg-gray-50 p-4 rounded-lg shadow-sm hover-scale">
                                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                    <div>
                                        <span class="text-sm text-gray-500">装备名称</span>
                                        <p class="font-medium">侦察干扰无人机群</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">类型</span>
                                        <p>电子战无人机</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">所属方队</span>
                                        <p>信息作战方队</p>
                                    </div>
                                </div>
                                <p class="mt-3 text-sm">
                                    <span class="text-gray-500">主要特点：</span>
                                    实施电磁压制与信号诱骗
                                </p>
                            </div>
                        </div>
                        
                        <div class="timeline-item relative">
                            <div class="absolute -left-32 top-0 bg-accent text-white text-xs font-bold px-3 py-1 rounded-full">
                                2025
                            </div>
                            <h4 class="text-lg font-semibold text-primary mb-2">体系化作战，三维覆盖</h4>
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                <div class="bg-gray-50 p-4 rounded-lg shadow-sm hover-scale relative">
                                    <span class="badge">1</span>
                                    <div>
                                        <span class="text-sm text-gray-500">装备名称</span>
                                        <p class="font-medium">无侦-8</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">类型</span>
                                        <p>高空高速战略侦察机</p>
                                    </div>
                                    <p class="mt-3 text-sm">
                                        <span class="text-gray-500">主要特点：</span>
                                        临近空间飞行，速度Ma5+，难被拦截
                                    </p>
                                </div>
                                <div class="bg-gray-50 p-4 rounded-lg shadow-sm hover-scale relative">
                                    <span class="badge">2</span>
                                    <div>
                                        <span class="text-sm text-gray-500">装备名称</span>
                                        <p class="font-medium">CH-7</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">类型</span>
                                        <p>大型隐身察打一体无人机</p>
                                    </div>
                                    <p class="mt-3 text-sm">
                                        <span class="text-gray-500">主要特点：</span>
                                        翼展27米，可挂载精确制导弹药
                                    </p>
                                </div>
                                <div class="bg-gray-50 p-4 rounded-lg shadow-sm hover-scale relative">
                                    <span class="badge">3</span>
                                    <div>
                                        <span class="text-sm text-gray-500">装备名称</span>
                                        <p class="font-medium">“蜂群-2025”</p>
                                    </div>
                                    <div>
                                        <span class="text-sm text-gray-500">类型</span>
                                        <p>微型作战无人机群</p>
                                    </div>
                                    <p class="mt-3 text-sm">
                                        <span class="text-gray-500">主要特点：</span>
                                        单次投放超200架，AI自主协同突防
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- 无人机图片展示 -->
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 my-8">
                        <div class="relative rounded-lg overflow-hidden shadow-md group">
                            <img src="images/3.1.jpg"" alt="大型无人机" class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-105">
                            <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent opacity-0 group-hover:opacity-100 transition-opacity flex flex-col justify-end p-4">
                                <h5 class="text-white font-semibold">攻击-11隐身无人攻击机</h5>
                                <p class="text-gray-200 text-sm">中国首款隐身无人作战飞机，具备强大的突防能力</p>
                            </div>
                        </div>
                        <div class="relative rounded-lg overflow-hidden shadow-md group">
                            <img src="images/3.2.png" alt="无人机蜂群" class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-105">
                            <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent opacity-0 group-hover:opacity-100 transition-opacity flex flex-col justify-end p-4">
                                <h5 class="text-white font-semibold">无人机蜂群作战系统</h5>
                                <p class="text-gray-200 text-sm">200架以上无人机协同作战，形成智能攻击网络</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-blue-50 border-l-4 border-primary p-4 rounded-r-lg mb-4">
                        <p class="italic text-gray-700">一位不愿具名的军事科技研究员表示：“无人化不是替代士兵，而是放大体系效能。2025年阅兵传递的信号是：中国已准备好打一场‘无人主导、有人决策’的智能化战争。”</p>
                    </div>
                    
                    <p class="text-gray-700">据《简氏防务周刊》分析，中国在无人机领域已实现“数量+质量”双领先。2024年珠海航展上，彩虹-7、翼龙-3等大型无人机已具备洲际作战潜力。而2025年阅兵展示的“蜂群”技术，更预示着未来战场将由“人指挥机器”转向“机器协同作战”。</p>
                </div>
            </div>
        </section>

        <!-- 大国长剑家族谱系 -->
        <section id="missiles" class="max-w-5xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden card-hover">
                <div class="p-8 md:p-10">
                    <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">四、“大国长剑”家族谱系：火箭军的战略威慑力跃升</h2>
                    <h3 class="text-xl font-semibold mb-4 text-secondary">从“区域拒止”到“全球到达”</h3>
                    
                    <div class="prose prose-lg max-w-none mb-8">
                        <p class="mb-4 text-indent-2">东风系列导弹是中国战略威慑的基石。与2015年相比，2025年火箭军方队的最大变化在于精度、生存力与突防能力的全面提升。东风-41采用三级固体燃料+公路机动+冷发射技术，可在任意地点快速发射；东风-17则利用钱学森弹道实现“无法拦截”的突防效果。</p>
                        <p class="text-indent-2">这种“高低搭配、常核兼备、全域覆盖”的导弹体系，使中国成为全球少数具备完整陆基战略核威慑能力的国家之一。正如《新时代的中国国防》白皮书所强调：“确保在任何情况下都能实施有效核反击。”</p>
                    </div>
                    
                    <div class="overflow-x-auto mb-8">
                        <table class="min-w-full divide-y divide-gray-200 shadow-sm">
                            <thead class="bg-primary text-white">
                                <tr>
                                    <th class="px-6 py-3 text-left text-xs font-medium uppercase tracking-wider">导弹型号</th>
                                    <th class="px-6 py-3 text-center text-xs font-medium uppercase tracking-wider">射程（公里）</th>
                                    <th class="px-6 py-3 text-center text-xs font-medium uppercase tracking-wider">弹头类型</th>
                                    <th class="px-6 py-3 text-left text-xs font-medium uppercase tracking-wider">主要特点</th>
                                    <th class="px-6 py-3 text-left text-xs font-medium uppercase tracking-wider">战略定位</th>
                                    <th class="px-6 py-3 text-center text-xs font-medium uppercase tracking-wider">首次阅兵</th>
                                </tr>
                            </thead>
                            <tbody class="bg-white divide-y divide-gray-200">
                                <tr class="hover:bg-gray-50 transition-colors">
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">东风-17</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">1800–2500</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">常规</td>
                                    <td class="px-6 py-4 text-sm">高超音速滑翔体，钱学森弹道</td>
                                    <td class="px-6 py-4 text-sm">突破反导系统</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">2019</td>
                                </tr>
                                <tr class="hover:bg-gray-50 transition-colors">
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">东风-21D</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">1500–2000</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">常规（反舰）</td>
                                    <td class="px-6 py-4 text-sm">机动再入，末端制导</td>
                                    <td class="px-6 py-4 text-sm">“航母杀手”，区域拒止</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">2015</td>
                                </tr>
                                <tr class="hover:bg-gray-50 transition-colors">
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">东风-26</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">3000–5000</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">常规/核</td>
                                    <td class="px-6 py-4 text-sm">核常兼备，公路机动</td>
                                    <td class="px-6 py-4 text-sm">覆盖关岛，第二岛链打击</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">2015</td>
                                </tr>
                                <tr class="hover:bg-gray-50 transition-colors">
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">东风-31AG</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">11000+</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">核</td>
                                    <td class="px-6 py-4 text-sm">固体燃料，越野机动发射</td>
                                    <td class="px-6 py-4 text-sm">陆基战略核威慑</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">2019</td>
                                </tr>
                                <tr class="hover:bg-gray-50 transition-colors">
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">东风-41</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">12000–15000</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">核（多弹头）</td>
                                    <td class="px-6 py-4 text-sm">MIRV技术，全球覆盖</td>
                                    <td class="px-6 py-4 text-sm">二次核反击主力</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">2019</td>
                                </tr>
                                <tr class="hover:bg-gray-50 transition-colors bg-blue-50">
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium font-semibold text-accent">东风-61</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">>15000</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center">核（多弹头）</td>
                                    <td class="px-6 py-4 text-sm">更大载荷，更强突防</td>
                                    <td class="px-6 py-4 text-sm">全球战略威慑升级</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm text-center font-semibold text-accent">2025</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    
                    <div class="bg-gray-50 p-4 rounded-lg text-sm text-gray-600 italic">
                        <p>说明：射程与性能参数综合自《简氏导弹与火箭系统年鉴2025》与中国官方披露信息。在2025年阅兵中出现一款新型洲际导弹，外形与尺寸明显大于东风-41，学界普遍称为“东风-61”。所有型号均在阅兵中实际展示。</p>
                    </div>
                    
                    <div class="mt-8 chart-container">
                        <canvas id="missileRangeChart"></canvas>
                    </div>
                    
                    <!-- 插入新图片 -->
                    <div class="mt-8">
                        <div class="bg-gray-50 rounded-lg p-3">
                            <div class="rounded-lg overflow-hidden shadow-md hover-scale flex justify-center">
                                <img src="images/4.4.jpg" alt="东风系列导弹家族" class="max-w-[85%] h-auto">
                                <div class="bg-gray-100 px-4 py-2 text-sm text-gray-600 w-full">
                                    东风系列导弹家族全景展示
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- 导弹系统图片 -->
                    <div class="mt-10 grid grid-cols-1 md:grid-cols-3 gap-4">
                        <div class="bg-gray-50 rounded-lg p-3 text-center">
                            <img src="images/4.1.jpg" alt="东风-17" class="w-full h-40 object-cover rounded mb-2">
                            <h5 class="font-medium text-sm">东风-17高超音速导弹</h5>
                            <p class="text-xs text-gray-500">中近程精确打击利器</p>
                        </div>
                        <div class="bg-gray-50 rounded-lg p-3 text-center">
                            <img src="images/4.2.jpg"" alt="东风-26" class="w-full h-40 object-cover rounded mb-2">
                            <h5 class="font-medium text-sm">东风-26中远程导弹</h5>
                            <p class="text-xs text-gray-500">核常兼备，全域慑战</p>
                        </div>
                        <div class="bg-gray-50 rounded-lg p-3 text-center">
                            <img src="images/4.3.jpg" alt="东风-41" class="w-full h-40 object-cover rounded mb-2">
                            <h5 class="font-medium text-sm">东风-41洲际导弹</h5>
                            <p class="text-xs text-gray-500">战略核力量的中坚</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 结论部分 -->
        <section id="conclusion" class="max-w-5xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-gradient-to-r from-primary to-secondary text-white rounded-xl shadow-xl p-8 md:p-10 animate-slide-up">
                <h2 class="text-3xl font-bold mb-6 border-l-4 border-accent pl-4">结论：从“看得见的钢铁”到“看不见的智能”</h2>
                <div class="prose prose-lg max-w-none text-gray-100">
                    <p class="mb-6 text-indent-2">十年三阅，变的不只是装备型号，更是战争思维与国防逻辑。</p>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
                        <div class="bg-white/10 backdrop-blur-sm p-5 rounded-lg hover:bg-white/15 transition-colors">
                            <div class="flex items-center mb-3">
                                <i class="fa fa-arrow-up text-accent text-xl mr-3"></i>
                                <h3 class="text-xl font-semibold">数量 → 质量</h3>
                            </div>
                            <p>装备更新率从30%跃升至62%，新质战斗力成为主力</p>
                        </div>
                        
                        <div class="bg-white/10 backdrop-blur-sm p-5 rounded-lg hover:bg-white/15 transition-colors">
                            <div class="flex items-center mb-3">
                                <i class="fa fa-sitemap text-accent text-xl mr-3"></i>
                                <h3 class="text-xl font-semibold">单一 → 联合</h3>
                            </div>
                            <p>陆军主导地位终结，海、空、天、网、电多维力量协同</p>
                        </div>
                        
                        <div class="bg-white/10 backdrop-blur-sm p-5 rounded-lg hover:bg-white/15 transition-colors">
                            <div class="flex items-center mb-3">
                                <i class="fa fa-cogs text-accent text-xl mr-3"></i>
                                <h3 class="text-xl font-semibold">机械 → 智能</h3>
                            </div>
                            <p>无人装备从辅助角色成长为体系核心，AI深度融入作战链条</p>
                        </div>
                        
                        <div class="bg-white/10 backdrop-blur-sm p-5 rounded-lg hover:bg-white/15 transition-colors">
                            <div class="flex items-center mb-3">
                                <i class="fa fa-shield text-accent text-xl mr-3"></i>
                                <h3 class="text-xl font-semibold">防御 → 慑战</h3>
                            </div>
                            <p>战略威慑能力从“存在性威慑”升级为“可信性威慑”</p>
                        </div>
                    </div>
                    
                    <div class="relative rounded-lg overflow-hidden mb-8">
                        <img src="images/4.5.jpg"" alt="现代化军队" class="w-full h-64 object-cover opacity-60">
                        <div class="absolute inset-0 flex items-center justify-center">
                            <p class="text-2xl md:text-3xl font-bold text-center px-4 text-shadow-lg">
                                从“钢铁洪流”到“智胜未来”的十年跨越
                            </p>
                        </div>
                    </div>
                    
                    <p class="mb-4">透过2025年九三阅兵的装备展示，我们可以清晰看到中国国防现代化已从“补课式”追赶进入“体系化”创新的新阶段。这种转变不仅体现在装备性能的代际跃升，更反映在战争形态认知与军事体系架构的深层变革。</p>
                    
                    <p>未来战争将是算法与火力的结合、智能与钢铁的融合。中国军队的十年跃迁，既是技术进步的必然结果，更是国家安全战略升级的集中体现——从“国土防御”到“全域机动作战”，从“数量规模型”到“质量效能型”，这支军队正以崭新面貌守护着国家发展与民族复兴的道路。</p>
                </div>
            </div>
        </section>
    </main>

    <!-- 页脚 -->
    <footer class="bg-dark text-white py-10">
        <div class="container mx-auto px-4">
            <div class="max-w-5xl mx-auto">
                <div class="flex flex-col md:flex-row justify-between items-center mb-8">
                    <div class="mb-6 md:mb-0">
                        <h3 class="text-xl font-bold flex items-center">
                            <i class="fa fa-line-chart mr-2 text-accent"></i>
                            <span>数据新闻</span>
                        </h3>
                        <p class="text-gray-400 mt-2">从数据视角解析中国国防现代化进程</p>
                    </div>
                    <div class="flex space-x-4">
                        <a href="#" class="w-10 h-10 rounded-full bg-primary/30 flex items-center justify-center hover:bg-accent transition-colors">
                            <i class="fa fa-twitter"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full bg-primary/30 flex items-center justify-center hover:bg-accent transition-colors">
                            <i class="fa fa-facebook"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full bg-primary/30 flex items-center justify-center hover:bg-accent transition-colors">
                            <i class="fa fa-linkedin"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full bg-primary/30 flex items-center justify-center hover:bg-accent transition-colors">
                            <i class="fa fa-weibo"></i>
                        </a>
                    </div>
                </div>
                
                <div class="border-t border-gray-700 pt-6 text-center text-gray-400 text-sm">
                    <p>© 2023级网络与新媒体5班 | 数据信息可视化 期末考核任务</p>
                    <p class="mt-2">小组成员：高崇峻 祝林林 肖恩晞 赵建华 多吉泽仁</p>
                </div>
            </div>
        </div>
    </footer>

    <!-- 返回顶部按钮 -->
    <button id="backToTop" class="fixed bottom-6 right-6 bg-accent text-white w-12 h-12 rounded-full flex items-center justify-center shadow-lg opacity-0 invisible transition-all duration-300 hover:bg-accent/90">
        <i class="fa fa-arrow-up"></i>
    </button>

    <script>
        // 导航栏滚动效果
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            const backToTop = document.getElementById('backToTop');
            const scrollIndicator = document.getElementById('scrollIndicator');
            
            // 导航栏效果
            if (window.scrollY > 50) {
                navbar.classList.add('py-2', 'shadow-md');
                navbar.classList.remove('py-3');
            } else {
                navbar.classList.add('py-3');
                navbar.classList.remove('py-2', 'shadow-md');
            }
            
            // 返回顶部按钮
            if (window.scrollY > 300) {
                backToTop.classList.remove('opacity-0', 'invisible');
                backToTop.classList.add('opacity-100', 'visible');
            } else {
                backToTop.classList.add('opacity-0', 'invisible');
                backToTop.classList.remove('opacity-100', 'visible');
            }
            
            // 滚动进度指示器
            const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
            const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrolled = (winScroll / height) * 100;
            scrollIndicator.style.width = scrolled + "%";
        });
        
        // 返回顶部功能
        document.getElementById('backToTop').addEventListener('click', function() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // 移动端菜单切换
        document.getElementById('menu-toggle').addEventListener('click', function() {
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenu.classList.toggle('hidden');
        });
        
        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                // 关闭移动端菜单（如果打开）
                document.getElementById('mobile-menu').classList.add('hidden');
                
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
        
        // 装备更新率图表
        const equipmentCtx = document.getElementById('equipmentChart').getContext('2d');
        new Chart(equipmentCtx, {
            type: 'bar',
            data: {
                labels: ['2015年', '2019年', '2025年'],
                datasets: [
                    {
                        label: '新型装备占比',
                        data: [30, 45, 62],
                        backgroundColor: '#e94560',
                        borderColor: '#e94560',
                        borderWidth: 1
                    },
                    {
                        label: '改进型装备占比',
                        data: [45, 35, 28],
                        backgroundColor: '#1a508b',
                        borderColor: '#1a508b',
                        borderWidth: 1
                    },
                    {
                        label: '老旧装备占比',
                        data: [25, 20, 10],
                        backgroundColor: '#0f3460',
                        borderColor: '#0f3460',
                        borderWidth: 1
                    }
                ]
            },
            options: {
                responsive: true,
                plugins: {
                    legend: {
                        position: 'top',
                    },
                    title: {
                        display: true,
                        text: '装备更新率变化趋势（%）'
                    },
                    tooltip: {
                        mode: 'index',
                        intersect: false,
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        max: 100,
                        title: {
                            display: true,
                            text: '占比（%）'
                        }
                    }
                },
                animation: {
                    duration: 2000,
                    easing: 'easeOutQuart'
                }
            }
        });
        
        // 军种结构图表
        const servicesCtx = document.getElementById('servicesChart').getContext('2d');
        new Chart(servicesCtx, {
            type: 'radar',
            data: {
                labels: ['陆军', '海军', '空军', '火箭军', '战略支援部队', '联勤保障/其他'],
                datasets: [
                    {
                        label: '2015年',
                        data: [58, 12, 10, 8, 0, 12],
                        backgroundColor: 'rgba(15, 52, 96, 0.2)',
                        borderColor: 'rgba(15, 52, 96, 1)',
                        pointBackgroundColor: 'rgba(15, 52, 96, 1)',
                        pointBorderColor: '#fff',
                        pointHoverBackgroundColor: '#fff',
                        pointHoverBorderColor: 'rgba(15, 52, 96, 1)'
                    },
                    {
                        label: '2019年',
                        data: [45, 15, 14, 12, 8, 6],
                        backgroundColor: 'rgba(26, 80, 139, 0.2)',
                        borderColor: 'rgba(26, 80, 139, 1)',
                        pointBackgroundColor: 'rgba(26, 80, 139, 1)',
                        pointBorderColor: '#fff',
                        pointHoverBackgroundColor: '#fff',
                        pointHoverBorderColor: 'rgba(26, 80, 139, 1)'
                    },
                    {
                        label: '2025年',
                        data: [32, 18, 16, 14, 12, 8],
                        backgroundColor: 'rgba(233, 69, 96, 0.2)',
                        borderColor: 'rgba(233, 69, 96, 1)',
                        pointBackgroundColor: 'rgba(233, 69, 96, 1)',
                        pointBorderColor: '#fff',
                        pointHoverBackgroundColor: '#fff',
                        pointHoverBorderColor: 'rgba(233, 69, 96, 1)'
                    }
                ]
            },
            options: {
                elements: {
                    line: {
                        borderWidth: 3
                    }
                },
                scales: {
                    r: {
                        angleLines: {
                            display: true
                        },
                        suggestedMin: 0,
                        suggestedMax: 60
                    }
                },
                plugins: {
                    title: {
                        display: true,
                        text: '军种结构占比变化（%）'
                    }
                },
                animation: {
                    duration: 2000,
                    easing: 'easeOutQuart'
                }
            }
        });
        
        // 导弹射程图表
        const missileCtx = document.getElementById('missileRangeChart').getContext('2d');
        new Chart(missileCtx, {
            type: 'horizontalBar',
            data: {
                labels: ['东风-17', '东风-21D', '东风-26', '东风-31AG', '东风-41', '（疑似）东风-51'],
                datasets: [{
                    label: '射程（公里）',
                    data: [2500, 2000, 5000, 11000, 15000, 16000],
                    backgroundColor: [
                        'rgba(26, 80, 139, 0.7)',
                        'rgba(26, 80, 139, 0.7)',
                        'rgba(26, 80, 139, 0.7)',
                        'rgba(15, 52, 96, 0.7)',
                        'rgba(15, 52, 96, 0.7)',
                        'rgba(233, 69, 96, 0.7)'
                    ],
                    borderColor: [
                        'rgba(26, 80, 139, 1)',
                        'rgba(26, 80, 139, 1)',
                        'rgba(26, 80, 139, 1)',
                        'rgba(15, 52, 96, 1)',
                        'rgba(15, 52, 96, 1)',
                        'rgba(233, 69, 96, 1)'
                    ],
                    borderWidth: 1
                }]
            },
            options: {
                indexAxis: 'y',
                scales: {
                    x: {
                        beginAtZero: true,
                        title: {
                            display: true,
                            text: '射程（公里）'
                        }
                    }
                },
                plugins: {
                    title: {
                        display: true,
                        text: '东风系列导弹射程对比'
                    }
                },
                animation: {
                    duration: 2000,
                    easing: 'easeOutQuart'
                }
            }
        });
        
        // 滚动动画
        const animateOnScroll = () => {
            const elements = document.querySelectorAll('.card-hover');
            
            elements.forEach(element => {
                const elementPosition = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (elementPosition < windowHeight - 100) {
                    element.classList.add('animate-fade-in');
                }
            });
        };
        
        // 初始加载和滚动时触发动画
        window.addEventListener('load', animateOnScroll);
        window.addEventListener('scroll', animateOnScroll);
    </script>
</body>
</html>
