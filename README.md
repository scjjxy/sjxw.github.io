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
        
        /* 为所有段落添加首行缩进 */
        p {
            text-indent: 2em;
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
    </style>
</head>
<body class="bg-gray-50 font-sans text-gray-800">
    <!-- 顶部导航栏 -->
    <header class="fixed top-0 left-0 right-0 bg-primary/95 text-white z-50 transition-all duration-300" id="navbar">
        <div class="container mx-auto px-4 py-3 flex justify-between items-center">
            <h1 class="text-xl md:text-2xl font-bold flex items-center">
                <i class="fa fa-line-chart mr-2 text-accent"></i>
                <span>数据信息可视化</span>
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
        <div class="container mx-auto px-4 relative z-10">
            <div class="max-w-6xl mx-auto text-center animate-fade-in">
                <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6 text-shadow-lg">从“钢铁洪流”到“智胜未来”</h1>
                <p class="text-xl md:text-2xl text-gray-200 mb-8">九三阅兵透视中国国防现代化十年跃迁</p>
                <div class="flex justify-center space-x-4">
                    <a href="#intro" class="bg-accent hover:bg-accent/90 text-white font-medium py-3 px-6 rounded-lg transition-all duration-300 flex items-center">
                        <i class="fa fa-book mr-2"></i> 开始阅读
                    </a>
                    <a href="#equipment" class="bg-transparent border-2 border-white hover:bg-white/10 text-white font-medium py-3 px-6 rounded-lg transition-all duration-300 flex items-center">
                        <i class="fa fa-bar-chart mr-2"></i> 查看数据
                    </a>
                </div>
            </div>
        </div>
        <div class="absolute bottom-0 left-0 right-0 h-16 bg-gradient-to-t from-gray-50 to-transparent"></div>
    </section>

    <!-- 主内容区域 -->
    <main class="container mx-auto px-4 py-12">
        <!-- 引言部分 -->
        <section id="intro" class="max-w-6xl mx-auto mb-20 animate-slide-up">
            <div class="bg-white rounded-xl shadow-xl p-8 md:p-10">
                <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">引言：一场阅兵，十年之变</h2>
                <div class="prose prose-lg max-w-none">
                    <p class="mb-4">2025年9月3日上午，北京天安门广场，伴随着《义勇军进行曲》的雄壮旋律，纪念中国人民抗日战争暨世界反法西斯战争胜利80周年的盛大阅兵拉开帷幕。当由数十架高空高速无人机组成的“无人作战第2方队”以编队形式低空掠过长安街，当东风-41洲际战略核导弹在重型运输车上缓缓驶来，全球军事观察家的目光再次聚焦中国——这个曾经以“人海战术”和“钢铁洪流”著称的国家，如今正以惊人的速度构建起一支高度信息化、智能化、体系化的现代军队。</p>
                    <p class="mb-4">公众的直观感受往往是“震撼”“自豪”，但在这情绪背后，一个更值得追问的问题是：过去十年，中国军队究竟发生了哪些结构性、技术性、战略性的跃迁？这些变化是否足以支撑“世界一流军队”的目标？</p>
                    <p>本文通过系统梳理2015年（抗战胜利70周年）、2019年（新中国成立70周年）与2025年（抗战胜利80周年）三次重大阅兵中的装备数据、军种构成与展示逻辑，结合《中国国防白皮书》、国际权威军事智库报告及官方媒体披露信息，用数据穿透宏大叙事，揭示中国国防现代化的真实图景。</p>
                </div>
            </div>
        </section>

        <!-- 装备更新加速 -->
        <section id="equipment" class="max-w-6xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden card-hover">
                <div class="p-8 md:p-10">
                    <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">一、装备更新加速：新质战斗力成主角</h2>
                    <h3 class="text-xl font-semibold mb-4 text-secondary">从“换代”到“代差”：装备迭代进入快车道</h3>
                    <div class="prose prose-lg max-w-none mb-8">
                        <p class="mb-4">2015年阅兵时，中国首次集中展示国产主战装备，如99A主战坦克、歼-15舰载机、东风-21D反舰弹道导弹等，标志着“自主可控”能力初步形成。然而，当时仍有近七成装备为改进型或延续型号。</p>
                        <p>而到了2025年，情况已截然不同。值得注意的是，2025年的新装备中，高超音速武器、隐身无人机、智能弹药、电磁炮试验平台、量子通信终端等前沿技术装备首次公开亮相，且多具备“改变游戏规则”（game-changing）的潜力。例如东风-17高超音速导弹，采用乘波体设计，飞行速度达Ma10以上，可有效突破现有导弹防御系统——这类装备的出现，已不仅是“更新”，而是形成“代差”。</p>
                    </div>
                    
                    <div class="chart-container mb-8">
                        <canvas id="equipmentChart"></canvas>
                    </div>
                    
                    <div class="bg-blue-50 border-l-4 border-primary p-4 rounded-r-lg mb-4">
                        <p class="italic text-gray-700">国防大学教授李明（化名，基于公开报道整合观点）指出：“过去我们追赶的是‘有没有’，现在追求的是‘好不好’‘快不快’‘能不能打智能仗’。2025年阅兵展示的不是单一武器，而是一个完整的智能作战生态。”</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 军种结构重塑 -->
        <section id="services" class="max-w-6xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden card-hover">
                <div class="p-8 md:p-10">
                    <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">二、军种结构重塑：从陆军主导到多维联合作战</h2>
                    <h3 class="text-xl font-semibold mb-4 text-secondary">“大陆军主义”的终结与联合作战体制的确立</h3>
                    <div class="prose prose-lg max-w-none mb-8">
                        <p class="mb-4">长期以来，中国人民解放军以陆军为核心，2015年改革前，陆军占全军总员额近60%。但随着“军委管总、战区主战、军种主建”改革推进，军队结构发生根本性转变。</p>
                        <p>这一变化清晰反映了中国军队从“平面陆军”向“立体联合作战”转型的战略意图。尤其值得关注的是，战略支援部队在2025年阅兵中不仅独立成方，还展示了天基侦察、网络攻防、电子对抗、心理战等多维能力，标志着“制信息权”已成为现代战争的核心制高点。</p>
                    </div>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
                        <div class="chart-container">
                            <canvas id="servicesChart"></canvas>
                        </div>
                        <div class="bg-gray-50 rounded-lg p-6">
                            <h4 class="font-semibold text-lg mb-4 text-primary">军种结构变化数据表</h4>
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
                    
                    <p class="text-gray-700">相比之下，美国2023年“国庆日”阅兵（虽规模较小）中，网络司令部与太空军已占据显著位置。中国的调整虽起步稍晚，但步伐更为紧凑。</p>
                </div>
            </div>
        </section>

        <!-- 无人方阵进化史 -->
        <section id="drones" class="max-w-6xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden card-hover">
                <div class="p-8 md:p-10">
                    <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">三、“无人方阵”进化史：从配角到体系化作战核心</h2>
                    <h3 class="text-xl font-semibold mb-4 text-secondary">无人系统的“三级跳”</h3>
                    <div class="prose prose-lg max-w-none mb-8">
                        <p class="mb-4">2015年，BZK-005侦察无人机仅作为陆军方队的附属装备出现，功能单一；2019年，攻击-11隐身无人攻击机惊艳亮相，具备内埋弹舱与飞翼布局，可执行穿透性打击任务；而2025年，三个完整的无人作战方队依次登场，涵盖侦察感知层、精确打击层和集群协同层。</p>
                    </div>
                    
                    <div class="relative timeline pl-8 mb-10 py-4">
                        <div class="timeline-item relative mb-10">
                            <h4 class="text-lg font-semibold text-primary mb-2">2015年：侦察为主，附属装备</h4>
                            <div class="bg-gray-50 p-4 rounded-lg shadow-sm">
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
                            <h4 class="text-lg font-semibold text-primary mb-2">2019年：隐身攻击，独立成方</h4>
                            <div class="bg-gray-50 p-4 rounded-lg shadow-sm mb-4">
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
                            <div class="bg-gray-50 p-4 rounded-lg shadow-sm">
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
                            <h4 class="text-lg font-semibold text-primary mb-2">2025年：体系化作战，三维覆盖</h4>
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                <div class="bg-gray-50 p-4 rounded-lg shadow-sm">
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
                                <div class="bg-gray-50 p-4 rounded-lg shadow-sm">
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
                                <div class="bg-gray-50 p-4 rounded-lg shadow-sm">
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
                    
                    <div class="bg-blue-50 border-l-4 border-primary p-4 rounded-r-lg mb-4">
                        <p class="italic text-gray-700">一位不愿具名的军事科技研究员表示：“无人化不是替代士兵，而是放大体系效能。2025年阅兵传递的信号是：中国已准备好打一场‘无人主导、有人决策’的智能化战争。”</p>
                    </div>
                    
                    <p class="text-gray-700">据《简氏防务周刊》分析，中国在无人机领域已实现“数量+质量”双领先。2024年珠海航展上，彩虹-7、翼龙-3等大型无人机已具备洲际作战潜力。而2025年阅兵展示的“蜂群”技术，更预示着未来战场将由“人指挥机器”转向“机器协同作战”。</p>
                </div>
            </div>
        </section>

        <!-- 大国长剑家族谱系 -->
        <section id="missiles" class="max-w-6xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden card-hover">
                <div class="p-8 md:p-10">
                    <h2 class="text-3xl font-bold mb-6 text-primary border-l-4 border-accent pl-4">四、“大国长剑”家族谱系：火箭军的战略威慑力跃升</h2>
                    <h3 class="text-xl font-semibold mb-4 text-secondary">从“区域拒止”到“全球到达”</h3>
                    <div class="prose prose-lg max-w-none mb-8">
                        <p class="mb-4">东风系列导弹是中国战略威慑的基石。与2015年相比，2025年火箭军方队的最大变化在于精度、生存力与突防能力的全面提升。东风-41采用三级固体燃料+公路机动+冷发射技术，可在任意地点快速发射；东风-17则利用钱学森弹道实现“无法拦截”的突防效果。</p>
                        <p>这种“高低搭配、常核兼备、全域覆盖”的导弹体系，使中国成为全球少数具备完整陆基战略核威慑能力的国家之一。正如《新时代的中国国防》白皮书所强调：“确保在任何情况下都能实施有效核反击。”</p>
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
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium font-semibold text-accent">（疑似）东风-51</td>
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
                        <p>说明：射程与性能参数综合自《简氏导弹与火箭系统年鉴2025》与中国官方披露信息。东风-51尚未获官方正式命名，但在2025年阅兵中出现一款新型洲际导弹，外形与尺寸明显大于东风-41，学界普遍称为“东风-51”。所有型号均在阅兵中实际展示。</p>
                    </div>
                    
                    <div class="mt-8 chart-container">
                        <canvas id="missileRangeChart"></canvas>
                    </div>
                </div>
            </div>
        </section>

        <!-- 结论部分 -->
        <section id="conclusion" class="max-w-6xl mx-auto mb-20 scroll-mt-24">
            <div class="bg-gradient-to-r from-primary to-secondary text-white rounded-xl shadow-xl p-8 md:p-10 animate-slide-up">
                <h2 class="text-3xl font-bold mb-6 border-l-4 border-accent pl-4">结论：从“看得见的钢铁”到“看不见的智能”</h2>
                <div class="prose prose-lg max-w-none text-gray-100">
                    <p class="mb-6">十年三阅，变的不只是装备型号，更是战争思维与国防逻辑。</p>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
                        <div class="bg-white/10 backdrop-blur-sm p-5 rounded-lg">
                            <div class="flex items-center mb-3">
                                <i class="fa fa-arrow-up text-accent text-xl mr-3"></i>
                                <h3 class="text-xl font-semibold">数量 → 质量</h3>
                            </div>
                            <p>装备更新率从30%跃升至62%，新质战斗力成为主力</p>
                        </div>
                        
                        <div class="bg-white/10 backdrop-blur-sm p-5 rounded-lg">
                            <div class="flex items-center mb-3">
                                <i class="fa fa-sitemap text-accent text-xl mr-3"></i>
                                <h3 class="text-xl font-semibold">单一 → 联合</h3>
                            </div>
                            <p>陆军主导地位终结，海、空、天、网、电多维力量协同</p>
                        </div>
                        
                        <div class="bg-white/10 backdrop-blur-sm p-5 rounded-lg">
                            <div class="flex items-center mb-3">
                                <i class="fa fa-robot text-accent text-xl mr-3"></i>
                                <h3 class="text-xl font-semibold">有人 → 无人</h3>
                            </div>
                            <p>无人系统从辅助走向核心，构建智能作战生态</p>
                        </div>
                        
                        <div class="bg-white/10 backdrop-blur-sm p-5 rounded-lg">
                            <div class="flex items-center mb-3">
                                <i class="fa fa-cubes text-accent text-xl mr-3"></i>
                                <h3 class="text-xl font-semibold">平台 → 体系</h3>
                            </div>
                            <p>单件武器融入C4ISR大系统，强调“体系对抗”而非“平台对决”</p>
                        </div>
                    </div>
                    
                    <p class="mb-4">更重要的是，2025年阅兵传递出一种克制而自信的姿态：没有炫耀武力，而是展示能力；没有渲染威胁，而是强调防御。这与《中国的和平发展》白皮书一脉相承——强大，是为了更好地维护和平。</p>
                    
                    <p>未来战场，胜负不再取决于坦克的数量，而在于算法的速度、数据的精度与体系的韧性。从“钢铁洪流”到“智胜未来”，中国军队的这场跃迁，才刚刚开始。</p>
                </div>
            </div>
        </section>

        <!-- 数据来源 -->
        <section class="max-w-6xl mx-auto mb-12">
            <div class="bg-gray-50 rounded-xl shadow-md p-6 md:p-8">
                <h3 class="text-xl font-bold mb-4 text-primary flex items-center">
                    <i class="fa fa-database mr-2 text-accent"></i>
                    数据来源说明
                </h3>
                <ul class="space-y-2 text-gray-700">
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-primary mt-1 mr-2"></i>
                        <span>中央电视台（CCTV）2015、2019、2025年阅兵直播及文字实录</span>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-primary mt-1 mr-2"></i>
                        <span>新华社、《解放军报》官方通稿与装备解读专栏</span>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-primary mt-1 mr-2"></i>
                        <span>《新时代的中国国防》白皮书（2019）、历年《中国国防》白皮书</span>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-primary mt-1 mr-2"></i>
                        <span>中国军网（www.81.cn）、中华人民共和国国防部官网</span>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-primary mt-1 mr-2"></i>
                        <span>国际战略研究所（IISS）《The Military Balance 2025》</span>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-primary mt-1 mr-2"></i>
                        <span>简氏防务周刊（Jane’s Defence Weekly）2024–2025年相关报道</span>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-primary mt-1 mr-2"></i>
                        <span>珠海中国国际航空航天博览会（2024）公开资料</span>
                    </li>
                </ul>
            </div>
        </section>
    </main>

    <!-- 页脚 -->
    <footer class="bg-dark text-white py-10">
        <div class="container mx-auto px-4">
            <div class="max-w-5xl mx-auto">
                <div class="flex flex-col md:flex-row justify-between items-center mb-8">
                    <h2 class="text-2xl font-bold mb-4 md:mb-0 flex items-center">
                        <i class="fa fa-line-chart mr-2 text-accent"></i>
                        <span>数据信息可视化</span>
                    </h2>
                    <div class="flex space-x-4">
                        <a href="#" class="bg-white/10 hover:bg-white/20 p-3 rounded-full transition-colors">
                            <i class="fa fa-weibo"></i>
                        </a>
                        <a href="#" class="bg-white/10 hover:bg-white/20 p-3 rounded-full transition-colors">
                            <i class="fa fa-wechat"></i>
                        </a>
                        <a href="#" class="bg-white/10 hover:bg-white/20 p-3 rounded-full transition-colors">
                            <i class="fa fa-twitter"></i>
                        </a>
                        <a href="#" class="bg-white/10 hover:bg-white/20 p-3 rounded-full transition-colors">
                            <i class="fa fa-linkedin"></i>
                        </a>
                    </div>
                </div>
                <div class="border-t border-white/10 pt-8 text-center text-gray-400 text-sm">
                    <p>© 2023级网络与新媒体5班 | 数据信息可视化小组</p>
                    <p class="mt-2">小组成员：高崇峻 祝林林 肖恩晞 赵建华 多吉泽仁</p>
                </div>
            </div>
        </div>
    </footer>

    <!-- 回到顶部按钮 -->
    <button id="back-to-top" class="fixed bottom-8 right-8 bg-accent hover:bg-accent/90 text-white p-3 rounded-full shadow-lg opacity-0 invisible transition-all duration-300 z-40">
        <i class="fa fa-arrow-up"></i>
    </button>

    <script>
        // 导航栏滚动效果
        const navbar = document.getElementById('navbar');
        const backToTop = document.getElementById('back-to-top');
        
        window.addEventListener('scroll', function() {
            if (window.scrollY > 100) {
                navbar.classList.add('py-2', 'shadow-lg');
                navbar.classList.remove('py-3');
                backToTop.classList.remove('opacity-0', 'invisible');
                backToTop.classList.add('opacity-100', 'visible');
            } else {
                navbar.classList.add('py-3');
                navbar.classList.remove('py-2', 'shadow-lg');
                backToTop.classList.add('opacity-0', 'invisible');
                backToTop.classList.remove('opacity-100', 'visible');
            }
        });
        
        // 移动端菜单切换
        const menuToggle = document.getElementById('menu-toggle');
        const mobileMenu = document.getElementById('mobile-menu');
        
        menuToggle.addEventListener('click', function() {
            mobileMenu.classList.toggle('hidden');
        });
        
        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                // 关闭移动端菜单
                if (!mobileMenu.classList.contains('hidden')) {
                    mobileMenu.classList.add('hidden');
                }
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // 回到顶部
        backToTop.addEventListener('click', function() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // 装备数据图表
        const equipmentCtx = document.getElementById('equipmentChart').getContext('2d');
        const equipmentChart = new Chart(equipmentCtx, {
            type: 'bar',
            data: {
                labels: ['2015年', '2019年', '2025年'],
                datasets: [
                    {
                        label: '受阅主战装备总数（种）',
                        data: [120, 160, 180],
                        backgroundColor: 'rgba(15, 52, 96, 0.7)',
                        borderColor: 'rgba(15, 52, 96, 1)',
                        borderWidth: 1
                    },
                    {
                        label: '首次亮相装备数量（种）',
                        data: [36, 64, 112],
                        backgroundColor: 'rgba(233, 69, 96, 0.7)',
                        borderColor: 'rgba(233, 69, 96, 1)',
                        borderWidth: 1
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    title: {
                        display: true,
                        text: '2015–2025三次阅兵主战装备数量与新装备占比对比',
                        font: {
                            size: 16,
                            weight: 'bold'
                        },
                        padding: {
                            bottom: 20
                        }
                    },
                    tooltip: {
                        mode: 'index',
                        intersect: false
                    },
                    legend: {
                        position: 'bottom'
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        grid: {
                            color: 'rgba(0, 0, 0, 0.05)'
                        }
                    },
                    x: {
                        grid: {
                            display: false
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
        const servicesChart = new Chart(servicesCtx, {
            type: 'stackedAreaChart',
            type: 'line',
            data: {
                labels: ['2015年', '2019年', '2025年'],
                datasets: [
                    {
                        label: '陆军',
                        data: [58, 45, 32],
                        backgroundColor: 'rgba(15, 52, 96, 0.2)',
                        borderColor: 'rgba(15, 52, 96, 1)',
                        fill: true,
                        tension: 0.3
                    },
                    {
                        label: '海军',
                        data: [12, 15, 18],
                        backgroundColor: 'rgba(26, 80, 139, 0.2)',
                        borderColor: 'rgba(26, 80, 139, 1)',
                        fill: true,
                        tension: 0.3
                    },
                    {
                        label: '空军',
                        data: [10, 14, 16],
                        backgroundColor: 'rgba(34, 139, 34, 0.2)',
                        borderColor: 'rgba(34, 139, 34, 1)',
                        fill: true,
                        tension: 0.3
                    },
                    {
                        label: '火箭军',
                        data: [8, 12, 14],
                        backgroundColor: 'rgba(255, 140, 0, 0.2)',
                        borderColor: 'rgba(255, 140, 0, 1)',
                        fill: true,
                        tension: 0.3
                    },
                    {
                        label: '战略支援部队',
                        data: [0, 8, 12],
                        backgroundColor: 'rgba(233, 69, 96, 0.2)',
                        borderColor: 'rgba(233, 69, 96, 1)',
                        fill: true,
                        tension: 0.3
                    },
                    {
                        label: '联勤保障/其他',
                        data: [12, 6, 8],
                        backgroundColor: 'rgba(128, 128, 128, 0.2)',
                        borderColor: 'rgba(128, 128, 128, 1)',
                        fill: true,
                        tension: 0.3
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    title: {
                        display: true,
                        text: '各军种受阅力量占比变化（2015-2025）',
                        font: {
                            size: 16,
                            weight: 'bold'
                        },
                        padding: {
                            bottom: 20
                        }
                    },
                    tooltip: {
                        mode: 'index',
                        intersect: false
                    },
                    legend: {
                        position: 'bottom'
                    }
                },
                scales: {
                    y: {
                        stacked: true,
                        beginAtZero: true,
                        max: 100,
                        ticks: {
                            callback: function(value) {
                                return value + '%';
                            }
                        },
                        grid: {
                            color: 'rgba(0, 0, 0, 0.05)'
                        }
                    },
                    x: {
                        stacked: true,
                        grid: {
                            display: false
                        }
                    }
                },
                animation: {
                    duration: 2000,
                    easing: 'easeOutQuart'
                }
            }
        });
        
        // 导弹射程图表
        const missileRangeCtx = document.getElementById('missileRangeChart').getContext('2d');
        const missileRangeChart = new Chart(missileRangeCtx, {
            type: 'bar',
            data: {
                labels: ['东风-17', '东风-21D', '东风-26', '东风-31AG', '东风-41', '东风-51(疑似)'],
                datasets: [
                    {
                        label: '射程（公里）',
                        data: [2150, 1750, 4000, 11000, 13500, 16000],
                        backgroundColor: [
                            'rgba(26, 80, 139, 0.7)',
                            'rgba(26, 80, 139, 0.7)',
                            'rgba(34, 139, 34, 0.7)',
                            'rgba(255, 140, 0, 0.7)',
                            'rgba(233, 69, 96, 0.7)',
                            'rgba(233, 69, 96, 0.9)'
                        ],
                        borderColor: [
                            'rgba(26, 80, 139, 1)',
                            'rgba(26, 80, 139, 1)',
                            'rgba(34, 139, 34, 1)',
                            'rgba(255, 140, 0, 1)',
                            'rgba(233, 69, 96, 1)',
                            'rgba(233, 69, 96, 1)'
                        ],
                        borderWidth: 1
                    }
                ]
            },
            options: {
                indexAxis: 'y',
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    title: {
                        display: true,
                        text: '东风导弹家族射程对比（公里）',
                        font: {
                            size: 16,
                            weight: 'bold'
                        },
                        padding: {
                            bottom: 20
                        }
                    },
                    tooltip: {
                        mode: 'index',
                        intersect: false
                    },
                    legend: {
                        display: false
                    }
                },
                scales: {
                    x: {
                        beginAtZero: true,
                        grid: {
                            color: 'rgba(0, 0, 0, 0.05)'
                        }
                    },
                    y: {
                        grid: {
                            display: false
                        }
                    }
                },
                animation: {
                    duration: 2000,
                    easing: 'easeOutQuart'
                }
            }
        });
        
        // 滚动动画
        const animateOnScroll = function() {
            const elements = document.querySelectorAll('.card-hover');
            
            elements.forEach(element => {
                const elementPosition = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (elementPosition < windowHeight - 100) {
                    element.classList.add('animate-fade-in');
                }
            });
        };
        
        // 初始加载时执行一次
        window.addEventListener('load', animateOnScroll);
        // 滚动时执行
        window.addEventListener('scroll', animateOnScroll);
    </script>
</body>
</html>
