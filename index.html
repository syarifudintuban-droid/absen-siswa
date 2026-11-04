<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aplikasi Absensi Barcode Siswa</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- QRCode.js for Square QR Code Generation -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <!-- HTML5-Qrcode for scanning -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html5-qrcode/2.3.8/html5-qrcode.min.js"></script>
    <!-- SheetJS for Excel export & import -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=Playfair+Display:wght@600;700&display=swap');
        
        body { font-family: 'Plus Jakarta Sans', sans-serif; }
        .font-card-title { font-family: 'Playfair Display', serif; }
        .tab-content { display: none; }
        .tab-content.active { display: block; }
        
        .card-precise-dim {
            width: 5.5cm !important;
            height: 8.7cm !important;
            box-sizing: border-box !important;
        }

        .card-emerald-bg {
            background-color: #064e3b !important;
            background-image: radial-gradient(rgba(245, 158, 11, 0.18) 1px, transparent 0) !important;
            background-size: 8px 8px !important;
            -webkit-print-color-adjust: exact !important;
            print-color-adjust: exact !important;
        }

        @keyframes scanFlash {
            0% { transform: scale(0.96); opacity: 0.8; }
            50% { transform: scale(1.02); opacity: 1; }
            100% { transform: scale(1); }
        }
        .scan-success-anim {
            animation: scanFlash 0.35s ease-out forwards;
        }

        .wall-clock {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: #0f172a;
            border: 3px solid #f59e0b;
            box-shadow: inset 0 0 8px rgba(0,0,0,0.8), 0 4px 10px rgba(0,0,0,0.3);
            position: relative;
            flex-shrink: 0;
        }
        .clock-center-dot {
            width: 6px;
            height: 6px;
            background: #f59e0b;
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 10;
        }
        .hand {
            position: absolute;
            bottom: 50%;
            left: 50%;
            transform-origin: bottom center;
            border-radius: 4px;
            z-index: 5;
        }
        .hour-hand {
            width: 3px;
            height: 22px;
            background: #ffffff;
            margin-left: -1.5px;
        }
        .minute-hand {
            width: 2px;
            height: 30px;
            background: #38bdf8;
            margin-left: -1px;
        }
        .second-hand {
            width: 1.5px;
            height: 34px;
            background: #ef4444;
            margin-left: -0.75px;
            z-index: 8;
        }
        .clock-num {
            position: absolute;
            font-size: 8px;
            font-weight: 800;
            color: #cbd5e1;
            text-align: center;
            width: 12px;
            height: 12px;
            line-height: 12px;
        }
        .num-12 { top: 2px; left: 50%; margin-left: -6px; }
        .num-3 { right: 2px; top: 50%; margin-top: -6px; }
        .num-6 { bottom: 2px; left: 50%; margin-left: -6px; }
        .num-9 { left: 2px; top: 50%; margin-top: -6px; }

        @media print {
            .no-print { display: none !important; }
            body { 
                background: white !important; 
                margin: 0 !important; 
                padding: 0 !important;
                -webkit-print-color-adjust: exact !important;
                print-color-adjust: exact !important;
            }
        }
    </style>
</head>
<body class="bg-gradient-to-br from-emerald-50 via-teal-50 to-green-50 text-slate-800 min-h-screen flex flex-col">

    <!-- LOGIN OVERLAY / MODAL -->
    <div id="loginOverlay" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 flex items-center justify-center p-4">
        <div class="bg-white rounded-2xl shadow-2xl max-w-sm w-full p-8 space-y-6 border border-emerald-100">
            <div class="text-center space-y-2">
                <div class="w-14 h-14 bg-emerald-600 text-white rounded-2xl mx-auto flex items-center justify-center shadow-lg shadow-emerald-200">
                    <i class="fa-solid fa-lock text-2xl"></i>
                </div>
                <h2 class="text-xl font-bold text-slate-800">Login Administrator</h2>
                <p class="text-xs text-slate-500">Masukkan username dan password untuk mengakses sistem absensi</p>
            </div>
            <form onsubmit="window.handleLogin(event)" class="space-y-4">
                <div>
                    <label class="block text-xs font-semibold text-slate-600 mb-1">Username:</label>
                    <div class="relative">
                        <span class="absolute inset-y-0 left-0 pl-3 flex items-center text-slate-400"><i class="fa-solid fa-user text-xs"></i></span>
                        <input type="text" id="loginUsername" required placeholder="admin" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl pl-9 pr-3.5 py-3 focus:outline-none focus:border-emerald-500 font-medium">
                    </div>
                </div>
                <div>
                    <label class="block text-xs font-semibold text-slate-600 mb-1">Password:</label>
                    <div class="relative">
                        <span class="absolute inset-y-0 left-0 pl-3 flex items-center text-slate-400"><i class="fa-solid fa-key text-xs"></i></span>
                        <input type="password" id="loginPassword" required placeholder="••••••••" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl pl-9 pr-3.5 py-3 focus:outline-none focus:border-emerald-500 font-medium">
                    </div>
                </div>
                <button type="submit" class="w-full bg-gradient-to-r from-emerald-500 to-teal-600 text-white py-3 rounded-xl text-xs font-bold shadow-md hover:brightness-105 transition-all">
                    Masuk ke Aplikasi
                </button>
            </form>
            <div class="text-center pt-2 border-t border-slate-100">
                <p class="text-[10px] text-slate-400">Default Login: Username <b class="text-slate-600">admin</b> | Password <b class="text-slate-600">admin123</b></p>
            </div>
        </div>
    </div>

    <!-- Header Navigation -->
    <header class="bg-gradient-to-r from-emerald-600 via-teal-600 to-emerald-700 shadow-lg sticky top-0 z-40 border-b border-emerald-400/30">
        <div class="max-w-7xl mx-auto px-4 py-3 flex justify-between items-center">
            <div class="flex items-center space-x-3">
                <div class="bg-white text-emerald-600 p-2.5 rounded-xl shadow-md font-bold flex items-center justify-center">
                    <i class="fa-solid fa-qrcode text-xl"></i>
                </div>
                <div>
                    <h1 class="text-white font-extrabold text-lg tracking-wide drop-shadow-sm" id="navSchoolName">Sistem Absensi Barcode</h1>
                    <p class="text-emerald-100 text-xs font-medium">Pencatatan Kehadiran, Terlambat, & Pulang Cepat</p>
                </div>
            </div>
            <div class="flex items-center space-x-2">
                <span id="currentDateDisplay" class="hidden sm:inline-flex items-center gap-2 bg-white/15 text-white backdrop-blur-md border border-white/20 text-xs px-4 py-1.5 rounded-full font-bold shadow-sm font-mono">
                    <i class="fa-regular fa-clock text-amber-300 animate-pulse"></i>
                    <span id="headerClock">--:--:--</span>
                </span>
            </div>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="flex-1 max-w-7xl w-full mx-auto px-4 py-6 grid grid-cols-1 md:grid-cols-4 gap-6">
        
        <!-- Sidebar Navigation -->
        <aside class="md:col-span-1 bg-white/90 backdrop-blur-md p-4 rounded-2xl shadow-sm border border-emerald-100/80 flex flex-col justify-between h-fit">
            <nav class="space-y-1.5">
                <button onclick="window.switchTab('scanner')" id="btn-scanner" class="tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all bg-gradient-to-r from-emerald-500 to-teal-600 text-white shadow-md shadow-emerald-200/50 font-semibold">
                    <i class="fa-solid fa-camera text-base w-6"></i>
                    <span>Scan Absensi</span>
                </button>
                <button onclick="window.switchTab('students')" id="btn-students" class="tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all text-slate-600 hover:bg-emerald-50 hover:text-emerald-700">
                    <i class="fa-solid fa-users text-base w-6"></i>
                    <span>Daftar Siswa</span>
                </button>
                <button onclick="window.switchTab('leave-entry')" id="btn-leave-entry" class="tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all text-slate-600 hover:bg-emerald-50 hover:text-emerald-700">
                    <i class="fa-solid fa-calendar-minus text-base w-6"></i>
                    <span>Izin & Cuti Siswa</span>
                </button>
                <button onclick="window.switchTab('template-entry')" id="btn-template-entry" class="tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all text-slate-600 hover:bg-emerald-50 hover:text-emerald-700">
                    <i class="fa-solid fa-table-cells text-base w-6"></i>
                    <span>Template & Input Data</span>
                </button>
                <button onclick="window.switchTab('generator')" id="btn-generator" class="tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all text-slate-600 hover:bg-emerald-50 hover:text-emerald-700">
                    <i class="fa-solid fa-id-card text-base w-6"></i>
                    <span>Kartu & Barcode Potret</span>
                </button>
                <button onclick="window.switchTab('reports')" id="btn-reports" class="tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all text-slate-600 hover:bg-emerald-50 hover:text-emerald-700">
                    <i class="fa-solid fa-chart-pie text-base w-6"></i>
                    <span>Laporan Kehadiran</span>
                </button>
                <button onclick="window.switchTab('settings')" id="btn-settings" class="tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all text-slate-600 hover:bg-emerald-50 hover:text-emerald-700">
                    <i class="fa-solid fa-gear text-base w-6"></i>
                    <span>Pengaturan</span>
                </button>
            </nav>
            <div class="pt-6 mt-6 border-t border-emerald-100/85 space-y-3 text-center">
                <button onclick="window.handleLogout()" class="w-full bg-rose-50 text-rose-600 border border-rose-200 px-3 py-2 rounded-xl text-xs font-semibold hover:bg-rose-100 transition-all flex items-center justify-center space-x-2">
                    <i class="fa-solid fa-right-from-bracket"></i><span>Keluar (Logout)</span>
                </button>
                <span class="block text-[10px] font-bold tracking-wider text-emerald-800 bg-emerald-100/70 px-3 py-1 rounded-full uppercase">Sistem Absensi v5.1</span>
            </div>
        </aside>

        <!-- Main Section Container -->
        <section class="md:col-span-3 space-y-6">

            <!-- SCANNER TAB -->
            <div id="tab-scanner" class="tab-content active space-y-6">
                <input type="text" id="hardwareScannerInput" class="opacity-0 absolute -top-24 -left-24 pointer-events-none" autocomplete="off">

                <div class="bg-gradient-to-r from-teal-600 to-emerald-600 text-white p-4 rounded-2xl shadow-sm flex flex-col sm:flex-row justify-between items-center gap-3">
                    <div class="flex items-center space-x-3">
                        <div class="bg-white/20 p-2.5 rounded-xl text-white">
                            <i class="fa-solid fa-barcode text-xl"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-sm">Mode Perangkat Scanner Barcode Fisik (USB / Wireless)</h3>
                            <p class="text-xs text-emerald-100" id="hardwareStatusText">Status: Siap menerima tembakan barcode dari perangkat luar</p>
                        </div>
                    </div>
                    <button onclick="window.toggleHardwareScannerMode()" id="btnHardwareToggle" class="bg-white text-teal-700 px-4 py-2 rounded-xl text-xs font-bold shadow hover:bg-emerald-50 transition-all">
                        <i class="fa-solid fa-plug mr-1.5"></i><span>Aktifkan Fokus Scanner</span>
                    </button>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-start">
                    <div class="lg:col-span-5 bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-sm border border-emerald-100/80 space-y-4">
                        <div class="flex justify-between items-center pb-3 border-b border-emerald-100/80">
                            <div>
                                <h2 class="text-base font-bold text-slate-800">Scanner Kamera</h2>
                                <p class="text-xs text-slate-500">Scan QR Code dari Kamera</p>
                            </div>
                            <div class="flex space-x-1.5">
                                <button onclick="window.startScanner()" class="bg-emerald-500 text-white px-3 py-1.5 rounded-xl text-xs font-semibold shadow hover:bg-emerald-600 transition-all">
                                    <i class="fa-solid fa-play"></i>
                                </button>
                                <button onclick="window.stopScanner()" class="bg-rose-50 text-rose-600 border border-rose-100 px-3 py-1.5 rounded-xl text-xs font-semibold hover:bg-rose-100 transition-all">
                                    <i class="fa-solid fa-stop"></i>
                                </button>
                            </div>
                        </div>

                        <div id="reader" class="w-full h-56 bg-slate-900/5 rounded-2xl overflow-hidden border-2 border-dashed border-emerald-200 relative flex items-center justify-center">
                            <div id="scannerPlaceholder" class="absolute inset-0 flex flex-col items-center justify-center text-slate-400 space-y-2 pointer-events-none transition-all duration-300">
                                <i class="fa-solid fa-camera-rotate text-3xl text-emerald-500 animate-pulse"></i>
                                <p class="text-xs font-medium">Klik tombol "Mulai" kamera</p>
                            </div>
                        </div>

                        <form onsubmit="window.handleManualScan(event)" class="flex gap-2 pt-1">
                            <input type="text" id="manualNIS" placeholder="Ketik/Scan NIS..." class="flex-1 bg-slate-50 border border-slate-200 text-xs rounded-xl px-3 py-2.5 focus:outline-none focus:border-emerald-500 font-mono">
                            <button type="submit" class="bg-emerald-600 text-white px-4 py-2.5 rounded-xl text-xs font-semibold shadow hover:bg-emerald-700 transition-all">
                                OK
                            </button>
                        </form>
                    </div>

                    <div class="lg:col-span-7 bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-md border-2 border-emerald-300 flex flex-col justify-between space-y-5">
                        <div class="border-b border-emerald-100 pb-3 flex flex-wrap justify-between items-center gap-2">
                            <h3 class="text-base font-extrabold text-slate-800 flex items-center gap-2">
                                <i class="fa-solid fa-circle-check text-emerald-600 text-lg"></i>
                                <span>Mode & Konfirmasi Absensi</span>
                            </h3>
                            <div class="bg-emerald-50 border border-emerald-200 px-3 py-1 rounded-full text-[11px] font-bold text-emerald-800 flex flex-wrap gap-2 sm:gap-3">
                                <span>Mulai Masuk: <b id="infoTimeStartIn" class="text-teal-600">06:00</b></span>
                                <span>Batas Tepat: <b id="infoTimeLateLimit" class="text-emerald-600">07:15</b></span>
                                <span>Plg Cepat: <b id="infoTimeEarly" class="text-amber-600">13:00</b></span>
                                <span>Pulang: <b id="infoTimeOut" class="text-emerald-600">15:00</b></span>
                            </div>
                        </div>

                        <div class="bg-gradient-to-r from-emerald-900 via-slate-900 to-teal-900 text-white p-4 rounded-2xl shadow-inner border border-emerald-600/50 flex items-center justify-between gap-3">
                            <div class="flex items-center space-x-3">
                                <div class="wall-clock">
                                    <div class="clock-num num-12">12</div>
                                    <div class="clock-num num-3">3</div>
                                    <div class="clock-num num-6">6</div>
                                    <div class="clock-num num-9">9</div>
                                    <div id="wallClockHour" class="hand hour-hand"></div>
                                    <div id="wallClockMinute" class="hand minute-hand"></div>
                                    <div id="wallClockSecond" class="hand second-hand"></div>
                                    <div class="clock-center-dot"></div>
                                </div>
                                <div>
                                    <span class="block text-[10px] uppercase tracking-wider text-emerald-200 font-bold">Waktu Real-Time Sistem</span>
                                    <span id="liveClockDate" class="text-xs font-semibold text-white">Hari, Tanggal Bulan Tahun</span>
                                    <span class="block text-[9px] text-emerald-300/80 font-medium mt-0.5"><i class="fa-solid fa-clock text-amber-400 mr-1"></i>Jam Dinding Sinkron Komputer</span>
                                </div>
                            </div>
                            <div class="text-right">
                                <span id="liveClockTime" class="text-2xl font-extrabold font-mono text-amber-300 tracking-wider">00:00:00</span>
                                <span class="block text-[9px] text-emerald-200 uppercase font-semibold">WIB / Real-Time</span>
                            </div>
                        </div>

                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                            <div>
                                <label class="block text-xs font-bold text-slate-700 mb-1">Pilih Mode Absensi Manual / Auto:</label>
                                <select id="scanModeSelect" class="w-full bg-slate-50 border border-slate-300 text-xs rounded-xl px-3 py-2 font-semibold focus:outline-none focus:border-emerald-500">
                                    <option value="AUTO">Otomatis (Masuk, Terlambat, Pulang)</option>
                                    <option value="Hadir">Hadir (Manual Override)</option>
                                    <option value="Terlambat">Terlambat (Manual Override)</option>
                                    <option value="Pulang Cepat">Pulang Cepat (Manual Override)</option>
                                    <option value="Izin">Izin (Manual)</option>
                                    <option value="Sakit">Sakit (Manual)</option>
                                    <option value="Cuti">Cuti (Manual)</option>
                                    <option value="Alpa">Alpa (Manual)</option>
                                </select>
                            </div>
                            
                            <div class="flex items-center pt-3 sm:pt-0">
                                <div class="w-full bg-slate-50 p-2 rounded-xl border border-slate-200 flex items-center space-x-2">
                                    <input type="checkbox" id="autoWhatsappToggle" class="w-4 h-4 text-emerald-600 rounded border-slate-300 focus:ring-emerald-500" checked>
                                    <label for="autoWhatsappToggle" class="text-xs font-bold text-slate-700 cursor-pointer">Kirim WhatsApp Ortu</label>
                                </div>
                            </div>
                        </div>

                        <div id="scanResultCardContainer" class="bg-gradient-to-br from-emerald-950 via-emerald-900 to-teal-950 text-white border-2 border-amber-400 p-5 rounded-2xl shadow-xl space-y-4 transition-all">
                            <div class="flex flex-col sm:flex-row items-center gap-5">
                                <div id="lastScanAvatar" class="w-28 h-36 bg-slate-800 rounded-2xl mx-auto flex-shrink-0 flex items-center justify-center shadow-lg border-2 border-amber-400 overflow-hidden relative">
                                    <i class="fa-solid fa-user text-5xl text-emerald-400"></i>
                                </div>
                                <div class="flex-1 text-center sm:text-left space-y-2">
                                    <span id="lastScanBadge" class="inline-block py-1 px-3.5 rounded-full text-xs font-extrabold uppercase tracking-wider bg-amber-400 text-slate-900 shadow">
                                        SIAP MEMINDAI
                                    </span>
                                    <div>
                                        <h2 id="lastScanName" class="text-xl font-extrabold text-amber-300 leading-tight">Belum Ada Scan</h2>
                                        <p id="lastScanClass" class="text-xs font-semibold text-emerald-200 mt-0.5">Silakan dekatkan barcode siswa ke kamera / scanner</p>
                                    </div>
                                    <div class="bg-emerald-900/80 p-2.5 rounded-xl border border-emerald-700/60 font-mono text-xs space-y-1 text-emerald-100">
                                        <div class="flex justify-between"><span>NIS / NISN:</span> <b id="lastScanNIS" class="text-white">-</b></div>
                                        <div class="flex justify-between"><span>Waktu Scan:</span> <b id="lastScanTime" class="text-amber-300">-</b></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-sm border border-emerald-100/80">
                    <div class="flex justify-between items-center pb-4 border-b border-emerald-100/80 mb-4">
                        <div>
                            <h3 class="text-base font-bold text-slate-800">Log Absensi Hari Ini</h3>
                            <p class="text-xs text-slate-500">Catatan masuk, terlambat, pulang, pulang cepat, izin, cuti, dan alpa hari ini</p>
                        </div>
                        <span id="todayCountBadge" class="bg-emerald-100 text-emerald-800 text-xs font-bold px-3 py-1 rounded-full">0 Siswa</span>
                    </div>
                    <div class="overflow-x-auto">
                        <table class="w-full text-left border-collapse text-xs">
                            <thead>
                                <tr class="bg-emerald-100/50 text-emerald-900 border-b border-emerald-200/60">
                                    <th class="p-3 font-semibold rounded-l-xl">Waktu Masuk</th>
                                    <th class="p-3 font-semibold">NIS</th>
                                    <th class="p-3 font-semibold">Nama Siswa</th>
                                    <th class="p-3 font-semibold">Kelas</th>
                                    <th class="p-3 font-semibold">Status Masuk</th>
                                    <th class="p-3 font-semibold">Waktu Pulang</th>
                                    <th class="p-3 font-semibold">Status Pulang</th>
                                    <th class="p-3 font-semibold text-right rounded-r-xl">Aksi</th>
                                </tr>
                            </thead>
                            <tbody id="todayLogTableBody" class="divide-y divide-slate-100">
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <!-- STUDENTS TAB -->
            <div id="tab-students" class="tab-content space-y-6">
                <div class="bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-sm border border-emerald-100/80">
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between pb-4 border-b border-emerald-100/80 mb-6 gap-4">
                        <div>
                            <h2 class="text-xl font-bold text-slate-800">Daftar Siswa & Data Orang Tua</h2>
                            <p class="text-xs text-slate-500">Kelola data siswa, NISN, Tempat Tanggal Lahir, pasfoto, dan kontak WhatsApp orang tua</p>
                        </div>
                        <div class="flex flex-wrap gap-2">
                            <button onclick="window.openStudentModal()" class="bg-gradient-to-r from-emerald-500 to-teal-600 text-white px-4 py-2.5 rounded-xl text-xs font-semibold shadow hover:brightness-105 transition-all flex items-center space-x-2">
                                <i class="fa-solid fa-user-plus"></i><span>Tambah Siswa</span>
                            </button>
                            <button onclick="window.openBulkModal()" class="bg-teal-600 text-white px-4 py-2.5 rounded-xl text-xs font-semibold shadow hover:bg-teal-700 transition-all flex items-center space-x-2">
                                <i class="fa-solid fa-file-arrow-up"></i><span>Import Massal</span>
                            </button>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-6">
                        <div>
                            <input type="text" id="searchStudentInput" oninput="window.renderStudentsTable()" placeholder="Cari berdasarkan nama, NIS, NISN, TTL, atau no. WA..." class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-4 py-3 focus:outline-none focus:border-emerald-500 focus:ring-2 focus:ring-emerald-200">
                        </div>
                        <div>
                            <select id="filterClassSelect" onchange="window.renderStudentsTable()" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-4 py-3 font-medium focus:outline-none focus:border-emerald-500 focus:ring-2 focus:ring-emerald-200">
                                <option value="">Semua Kelas</option>
                            </select>
                        </div>
                    </div>

                    <div class="overflow-x-auto">
                        <table class="w-full text-left border-collapse text-xs">
                            <thead>
                                <tr class="bg-emerald-100/50 text-emerald-900 border-b border-emerald-200/60">
                                    <th class="p-3 font-semibold rounded-l-xl">Foto</th>
                                    <th class="p-3 font-semibold">Status Foto</th>
                                    <th class="p-3 font-semibold">NIS / NISN</th>
                                    <th class="p-3 font-semibold">Nama Siswa</th>
                                    <th class="p-3 font-semibold">Tempat, Tgl Lahir (TTL)</th>
                                    <th class="p-3 font-semibold">Kelas</th>
                                    <th class="p-3 font-semibold">No. WA Ortu</th>
                                    <th class="p-3 font-semibold text-right rounded-r-xl">Aksi</th>
                                </tr>
                            </thead>
                            <tbody id="studentsTableBody" class="divide-y divide-slate-100">
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <!-- TAB: IZIN & CUTI SISWA -->
            <div id="tab-leave-entry" class="tab-content space-y-6">
                <div class="bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-sm border border-emerald-100/80 space-y-6">
                    <div class="pb-4 border-b border-emerald-100/80">
                        <h2 class="text-xl font-bold text-slate-800">Form Permohonan Izin & Cuti Siswa</h2>
                        <p class="text-xs text-slate-500">Catat keterangan Izin, Sakit, atau Cuti siswa untuk rentang hari tertentu</p>
                    </div>

                    <form onsubmit="window.saveLeaveEntry(event)" class="bg-slate-50/70 border border-emerald-100 p-5 rounded-2xl space-y-4">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-xs font-semibold text-slate-700 mb-1">Pilih Siswa:</label>
                                <select id="leaveStudentSelect" required class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 font-medium focus:outline-none focus:border-emerald-500">
                                </select>
                            </div>
                            <div>
                                <label class="block text-xs font-semibold text-slate-700 mb-1">Jenis Keterangan:</label>
                                <select id="leaveTypeSelect" required class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 font-medium focus:outline-none focus:border-emerald-500">
                                    <option value="Izin">Izin</option>
                                    <option value="Sakit">Sakit</option>
                                    <option value="Cuti">Cuti Siswa</option>
                                    <option value="Alpa">Alpa (Tanpa Keterangan)</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-xs font-semibold text-slate-700 mb-1">Dari Tanggal:</label>
                                <input type="date" id="leaveStartDate" required class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500">
                            </div>
                            <div>
                                <label class="block text-xs font-semibold text-slate-700 mb-1">Sampai Tanggal:</label>
                                <input type="date" id="leaveEndDate" required class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500">
                            </div>
                            <div class="md:col-span-2">
                                <label class="block text-xs font-semibold text-slate-700 mb-1">Alasan / Catatan Keterangan:</label>
                                <input type="text" id="leaveReason" placeholder="Contoh: Acara keluarga / Demam / Cuti Umrah" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500">
                            </div>
                        </div>

                        <div class="flex items-center justify-between pt-2">
                            <span class="text-[11px] text-slate-500"><i class="fa-solid fa-circle-info text-emerald-600 mr-1"></i>Data otomatis dimasukkan ke laporan absensi sesuai tanggal.</span>
                            <button type="submit" class="bg-gradient-to-r from-emerald-500 to-teal-600 text-white px-6 py-2.5 rounded-xl text-xs font-bold shadow hover:brightness-105 transition-all flex items-center space-x-2">
                                <i class="fa-solid fa-floppy-disk"></i><span>Simpan Izin/Cuti</span>
                            </button>
                        </div>
                    </form>

                    <div class="space-y-3 pt-4 border-t border-slate-100">
                        <h3 class="text-base font-bold text-slate-800">Daftar Pengajuan Izin & Cuti Tercatat</h3>
                        <div class="overflow-x-auto">
                            <table class="w-full text-left border-collapse text-xs">
                                <thead>
                                    <tr class="bg-emerald-100/50 text-emerald-900 border-b border-emerald-200/60">
                                        <th class="p-3 font-semibold rounded-l-xl">No</th>
                                        <th class="p-3 font-semibold">NIS</th>
                                        <th class="p-3 font-semibold">Nama Siswa</th>
                                        <th class="p-3 font-semibold">Kelas</th>
                                        <th class="p-3 font-semibold">Jenis</th>
                                        <th class="p-3 font-semibold">Periode Tanggal</th>
                                        <th class="p-3 font-semibold">Alasan</th>
                                        <th class="p-3 font-semibold text-right rounded-r-xl">Aksi</th>
                                    </tr>
                                </thead>
                                <tbody id="leaveTableBody" class="divide-y divide-slate-100">
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- TEMPLATE & INPUT DATA TAB -->
            <div id="tab-template-entry" class="tab-content space-y-6">
                <div class="bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-sm border border-emerald-100/80 space-y-6">
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between pb-4 border-b border-emerald-100/80 gap-4">
                        <div>
                            <h2 class="text-xl font-bold text-slate-800">Template & Input Data Siswa Per Kolom</h2>
                            <p class="text-xs text-slate-500">Isi data siswa dalam grid tabel interaktif (Termasuk TTL, NISN, & URL Foto)</p>
                        </div>
                        <div class="flex flex-wrap gap-2">
                            <button onclick="window.downloadExcelTemplate()" class="bg-emerald-50 text-emerald-700 border border-emerald-200 px-3.5 py-2.5 rounded-xl text-xs font-semibold hover:bg-emerald-100 transition-all flex items-center space-x-2">
                                <i class="fa-solid fa-file-arrow-down text-emerald-600"></i><span>Download Format Excel</span>
                            </button>
                            <label class="bg-teal-600 text-white px-3.5 py-2.5 rounded-xl text-xs font-semibold shadow hover:bg-teal-700 transition-all cursor-pointer flex items-center space-x-2">
                                <i class="fa-solid fa-file-import"></i><span>Upload Excel / CSV</span>
                                <input type="file" id="excelFileInput" accept=".xlsx, .xls, .csv" onchange="window.handleExcelFileUpload(event)" class="hidden">
                            </label>
                        </div>
                    </div>

                    <div class="space-y-4">
                        <div class="flex flex-col sm:flex-row justify-between items-center gap-2">
                            <div class="flex items-center space-x-2">
                                <span class="text-xs font-bold text-slate-700">Grid Input Kolom Data Siswa</span>
                                <span class="text-[10px] bg-emerald-100 text-emerald-800 font-medium px-2 py-0.5 rounded-full">Format Spreadsheet</span>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="window.addGridRow()" class="bg-emerald-100 text-emerald-800 border border-emerald-200 px-3 py-1.5 rounded-xl text-xs font-semibold hover:bg-emerald-200 transition-all flex items-center space-x-1">
                                    <i class="fa-solid fa-plus text-xs"></i><span>Tambah Baris</span>
                                </button>
                                <button onclick="window.clearGridRows()" class="bg-rose-50 text-rose-600 border border-rose-100 px-3 py-1.5 rounded-xl text-xs font-semibold hover:bg-rose-100 transition-all">
                                    Bersihkan Baris
                                </button>
                            </div>
                        </div>

                        <div class="overflow-x-auto border border-emerald-200/80 rounded-2xl shadow-xs bg-slate-50/50 p-1">
                            <table class="w-full text-left border-collapse text-xs">
                                <thead>
                                    <tr class="bg-emerald-600 text-white">
                                        <th class="p-3 font-semibold rounded-tl-xl w-10 text-center">No</th>
                                        <th class="p-3 font-semibold w-24">NIS</th>
                                        <th class="p-3 font-semibold w-28">NISN</th>
                                        <th class="p-3 font-semibold min-w-[150px]">Nama Lengkap</th>
                                        <th class="p-3 font-semibold min-w-[140px]">Tempat, Tgl Lahir</th>
                                        <th class="p-3 font-semibold w-28">Kelas</th>
                                        <th class="p-3 font-semibold w-32">No. WA Ortu</th>
                                        <th class="p-3 font-semibold min-w-[120px]">URL Foto (Opsional)</th>
                                        <th class="p-3 font-semibold rounded-tr-xl w-10 text-center">Hapus</th>
                                    </tr>
                                </thead>
                                <tbody id="gridTableBody" class="bg-white divide-y divide-slate-100">
                                </tbody>
                            </table>
                        </div>

                        <div class="pt-2 flex flex-col sm:flex-row justify-between items-center gap-4">
                            <p class="text-[11px] text-slate-500">
                                <i class="fa-solid fa-circle-info text-emerald-600 mr-1"></i>Isi data pada kolom di atas, lalu klik <b>"Simpan Semua Data Siswa"</b> untuk memasukkan ke database.
                            </p>
                            <button onclick="window.saveGridData()" class="w-full sm:w-auto bg-gradient-to-r from-emerald-500 to-teal-600 text-white px-6 py-3 rounded-xl text-xs font-bold shadow-md hover:brightness-105 transition-all flex items-center justify-center space-x-2">
                                <i class="fa-solid fa-floppy-disk text-sm"></i><span>Simpan Semua Data Siswa</span>
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- GENERATOR TAB -->
            <div id="tab-generator" class="tab-content space-y-6">
                <div class="bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-sm border border-emerald-100/80">
                    <div class="pb-4 border-b border-emerald-100/80 mb-6">
                        <h2 class="text-xl font-bold text-slate-800">Cetak Kartu Pelajar Potret Elegan (5.5 x 8.7 cm)</h2>
                        <p class="text-xs text-slate-500">Kartu Pelajar Ukuran Standar ISO dengan Logo Lembaga & Barcode Presisi</p>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 items-start">
                        <div class="space-y-4 bg-slate-50/60 p-4 rounded-2xl border border-emerald-100">
                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Filter Kelas:</label>
                                <select id="genClassSelect" onchange="window.updateGeneratorStudentList()" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3 py-2.5 font-medium focus:outline-none focus:border-emerald-500"></select>
                            </div>
                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Pilih Siswa:</label>
                                <select id="genStudentSelect" onchange="window.previewCard()" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3 py-2.5 font-medium focus:outline-none focus:border-emerald-500"></select>
                            </div>
                            <div class="space-y-2">
                                <button onclick="window.printCard()" class="w-full bg-gradient-to-r from-emerald-600 via-teal-600 to-emerald-700 text-white px-4 py-3 rounded-xl text-xs font-bold shadow-md hover:brightness-105 transition-all flex items-center justify-center space-x-2">
                                    <i class="fa-solid fa-print"></i><span>Cetak Kartu Tunggal (Kertas 7 x 9 cm)</span>
                                </button>
                                <button onclick="window.printBulkCards()" class="w-full bg-teal-800 text-white px-4 py-2.5 rounded-xl text-xs font-bold shadow hover:bg-teal-900 transition-all flex items-center justify-center space-x-2">
                                    <i class="fa-solid fa-clone"></i><span>Cetak Massal A4 (9 Kartu / Halaman)</span>
                                </button>
                            </div>
                        </div>

                        <div class="md:col-span-2 flex flex-col justify-center items-center bg-slate-100/80 border border-emerald-200 rounded-2xl p-6">
                            <span class="text-xs font-semibold text-emerald-800 mb-3 flex items-center gap-1.5"><i class="fa-solid fa-crown text-amber-500"></i> Pratinjau Kartu Pelajar Resmi dengan Logo Lembaga</span>
                            
                            <div id="cardPreviewContainer" class="card-precise-dim card-emerald-bg text-slate-100 rounded-2xl shadow-xl relative overflow-hidden flex flex-col justify-between p-3 border border-amber-400/40">
                                <div class="absolute inset-1.5 border border-amber-400/30 rounded-xl pointer-events-none z-20"></div>

                                <div class="relative z-10 pt-0.5 border-b border-amber-400/20 pb-1 flex items-center justify-center space-x-2">
                                    <div class="w-6 h-6 flex items-center justify-center overflow-hidden flex-shrink-0">
                                        <img id="cardSchoolLogo" src="https://placehold.co/100x100/064e3b/ffffff?text=LOGO" alt="Logo" class="w-full h-full object-contain">
                                    </div>
                                    <div class="text-center">
                                        <h4 id="cardSchoolName" class="font-bold text-[8.5px] leading-tight uppercase tracking-wider text-amber-300 font-card-title line-clamp-1">SMA NEGERI 1 UNGGUL</h4>
                                        <p class="text-[5px] text-emerald-200/80 tracking-widest uppercase font-semibold">KARTU TANDA PELAJAR RESMI</p>
                                    </div>
                                </div>

                                <div class="flex flex-col items-center text-center space-y-1 my-auto relative z-10">
                                    <div class="p-0.5 rounded-xl bg-gradient-to-tr from-amber-500 via-amber-200 to-amber-500 shadow-sm">
                                        <div class="w-22 h-28 bg-slate-900 rounded-lg overflow-hidden flex items-center justify-center border border-emerald-800">
                                            <img id="cardStudentPhoto" src="https://placehold.co/140x180/064e3b/ffffff?text=FOTO" alt="Foto Siswa" class="w-full h-full object-cover">
                                        </div>
                                    </div>

                                    <div class="w-full space-y-0.5 px-0.5">
                                        <h3 id="cardStudentName" class="font-extrabold text-[9.5px] text-white line-clamp-1 leading-tight tracking-wide uppercase">NAMA SISWA</h3>
                                        <div class="inline-block bg-amber-400/20 border border-amber-400/40 text-amber-300 font-bold text-[6.5px] px-2 py-0.2 rounded-full uppercase tracking-wider">
                                            <span id="cardStudentClass">X IPA 1</span>
                                        </div>
                                        
                                        <div class="bg-emerald-950/90 rounded-lg py-1 px-2 text-[6.5px] font-mono space-y-0.5 border border-emerald-800/80 text-emerald-100 leading-none">
                                            <div class="flex justify-between"><span class="text-emerald-300/60">NIS:</span> <span id="cardStudentNIS" class="font-bold text-amber-300">1001</span></div>
                                            <div class="flex justify-between"><span class="text-emerald-300/60">NISN:</span> <span id="cardStudentNISN" class="font-bold text-white">0051234567</span></div>
                                            <div class="flex justify-between border-t border-emerald-800/60 pt-0.5 text-[6px]"><span class="text-emerald-300/60">TTL:</span> <span id="cardStudentTTL" class="font-semibold text-emerald-100 truncate max-w-[105px]">Jakarta, 12-05-2008</span></div>
                                        </div>
                                    </div>
                                </div>

                                <div class="bg-emerald-950/90 rounded-xl p-1 flex flex-col items-center justify-center border border-amber-400/30 relative z-10 shadow-inner">
                                    <div class="bg-white p-0.5 rounded-lg border border-slate-200 flex items-center justify-center">
                                        <div id="qrcodeElement" class="w-[70px] h-[70px] flex items-center justify-center"></div>
                                    </div>
                                    <p class="text-[5px] font-bold text-amber-300 uppercase tracking-widest mt-0.5">VERIFIKASI ABSENSI</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- REPORTS TAB -->
            <div id="tab-reports" class="tab-content space-y-6">
                <div class="bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-sm border border-emerald-100/80 space-y-6">
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between pb-4 border-b border-emerald-100/80 gap-4">
                        <div>
                            <h2 class="text-xl font-bold text-slate-800">Pusat Laporan Kehadiran</h2>
                            <p class="text-xs text-slate-500">Rekapitulasi kehadiran harian, bulanan, semester, & Grafik Top 10 Bolos</p>
                        </div>
                        <button onclick="window.exportActiveReportToExcel()" class="bg-emerald-600 text-white px-4 py-2.5 rounded-xl text-xs font-semibold shadow hover:bg-emerald-700 transition-all flex items-center space-x-2">
                            <i class="fa-solid fa-file-excel"></i><span>Export Laporan ke Excel</span>
                        </button>
                    </div>

                    <div class="flex space-x-2 border-b border-slate-200 pb-3">
                        <button onclick="window.switchReportSubTab('daily')" id="btn-rep-daily" class="rep-sub-tab px-4 py-2 rounded-xl text-xs font-bold transition-all bg-emerald-600 text-white shadow-sm">Laporan Harian</button>
                        <button onclick="window.switchReportSubTab('monthly')" id="btn-rep-monthly" class="rep-sub-tab px-4 py-2 rounded-xl text-xs font-bold transition-all bg-slate-100 text-slate-600 hover:bg-emerald-50">Laporan Bulanan & Grafik Bolos</button>
                        <button onclick="window.switchReportSubTab('semester')" id="btn-rep-semester" class="rep-sub-tab px-4 py-2 rounded-xl text-xs font-bold transition-all bg-slate-100 text-slate-600 hover:bg-emerald-50">Laporan Semester & Grafik Bolos</button>
                    </div>

                    <!-- Daily Report View -->
                    <div id="rep-sub-daily" class="rep-sub-content space-y-4">
                        <div class="flex flex-wrap gap-4 items-center bg-slate-50 p-4 rounded-2xl border border-emerald-100">
                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Pilih Tanggal:</label>
                                <input type="date" id="reportDailyDate" onchange="window.renderReports()" class="bg-white border border-slate-200 text-xs rounded-xl px-3 py-2 font-medium focus:outline-none focus:border-emerald-500">
                            </div>
                        </div>
                        <div class="overflow-x-auto">
                            <table class="w-full text-left border-collapse text-xs">
                                <thead>
                                    <tr class="bg-emerald-100/50 text-emerald-900 border-b border-emerald-200/60">
                                        <th class="p-3 font-semibold rounded-l-xl">No</th>
                                        <th class="p-3 font-semibold">NIS</th>
                                        <th class="p-3 font-semibold">Nama Siswa</th>
                                        <th class="p-3 font-semibold">Kelas</th>
                                        <th class="p-3 font-semibold">Masuk</th>
                                        <th class="p-3 font-semibold">Pulang</th>
                                        <th class="p-3 font-semibold rounded-r-xl">Keterangan</th>
                                    </tr>
                                </thead>
                                <tbody id="reportDailyTableBody" class="divide-y divide-slate-100"></tbody>
                            </table>
                        </div>
                    </div>

                    <!-- Monthly Report View -->
                    <div id="rep-sub-monthly" class="rep-sub-content space-y-6 hidden">
                        <div class="flex flex-wrap gap-4 items-center bg-slate-50 p-4 rounded-2xl border border-emerald-100">
                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Pilih Bulan:</label>
                                <input type="month" id="reportMonthInput" onchange="window.renderReports()" class="bg-white border border-slate-200 text-xs rounded-xl px-3 py-2 font-medium focus:outline-none focus:border-emerald-500">
                            </div>
                        </div>

                        <!-- GRAFIK TOP 10 SISWA SERING BOLOS (BULANAN) -->
                        <div class="bg-gradient-to-br from-rose-950 via-slate-900 to-rose-900 text-white p-5 rounded-2xl shadow-lg border border-rose-500/40 space-y-4">
                            <div class="flex items-center justify-between pb-3 border-b border-rose-800/60">
                                <h3 class="font-extrabold text-sm flex items-center gap-2 text-rose-300">
                                    <i class="fa-solid fa-chart-column text-rose-400"></i> Grafik Top 10 Siswa Sering Bolos / Alpa (Bulan Ini)
                                </h3>
                                <span class="text-[10px] bg-rose-500/20 text-rose-300 border border-rose-500/30 px-2.5 py-1 rounded-full font-bold uppercase tracking-wider">Statistik Kedisiplinan</span>
                            </div>
                            <div id="monthlyTopBolosChartContainer" class="space-y-2.5 py-1">
                                <!-- Rendered via JS -->
                            </div>
                        </div>

                        <div class="overflow-x-auto">
                            <table class="w-full text-left border-collapse text-xs">
                                <thead>
                                    <tr class="bg-emerald-100/50 text-emerald-900 border-b border-emerald-200/60">
                                        <th class="p-3 font-semibold rounded-l-xl">No</th>
                                        <th class="p-3 font-semibold">NIS</th>
                                        <th class="p-3 font-semibold">Nama Siswa</th>
                                        <th class="p-3 font-semibold">Kelas</th>
                                        <th class="p-3 font-semibold text-center">Hadir</th>
                                        <th class="p-3 font-semibold text-center">Terlambat</th>
                                        <th class="p-3 font-semibold text-center">Pulang Cepat</th>
                                        <th class="p-3 font-semibold text-center">Izin/Sakit/Cuti</th>
                                        <th class="p-3 font-semibold text-center rounded-r-xl text-rose-700 font-extrabold">Alpa (Bolos)</th>
                                    </tr>
                                </thead>
                                <tbody id="reportMonthlyTableBody" class="divide-y divide-slate-100"></tbody>
                            </table>
                        </div>
                    </div>

                    <!-- Semester Report View -->
                    <div id="rep-sub-semester" class="rep-sub-content space-y-6 hidden">
                        <div class="flex flex-wrap gap-4 items-center bg-slate-50 p-4 rounded-2xl border border-emerald-100">
                            <div>
                                <label class="block text-xs font-semibold text-slate-600 mb-1">Pilih Semester:</label>
                                <select id="reportSemesterSelect" onchange="window.renderReports()" class="bg-white border border-slate-200 text-xs rounded-xl px-3 py-2 font-medium focus:outline-none focus:border-emerald-500">
                                    <option value="1">Semester Ganjil (Juli - Desember)</option>
                                    <option value="2">Semester Genap (Januari - Juni)</option>
                                </select>
                            </div>
                        </div>

                        <!-- GRAFIK TOP 10 SISWA SERING BOLOS (SEMESTER) -->
                        <div class="bg-gradient-to-br from-rose-950 via-slate-900 to-rose-900 text-white p-5 rounded-2xl shadow-lg border border-rose-500/40 space-y-4">
                            <div class="flex items-center justify-between pb-3 border-b border-rose-800/60">
                                <h3 class="font-extrabold text-sm flex items-center gap-2 text-rose-300">
                                    <i class="fa-solid fa-chart-column text-rose-400"></i> Grafik Top 10 Siswa Sering Bolos / Alpa (Semester Ini)
                                </h3>
                                <span class="text-[10px] bg-rose-500/20 text-rose-300 border border-rose-500/30 px-2.5 py-1 rounded-full font-bold uppercase tracking-wider">Statistik Kedisiplinan</span>
                            </div>
                            <div id="semesterTopBolosChartContainer" class="space-y-2.5 py-1">
                                <!-- Rendered via JS -->
                            </div>
                        </div>

                        <div class="overflow-x-auto">
                            <table class="w-full text-left border-collapse text-xs">
                                <thead>
                                    <tr class="bg-emerald-100/50 text-emerald-900 border-b border-emerald-200/60">
                                        <th class="p-3 font-semibold rounded-l-xl">No</th>
                                        <th class="p-3 font-semibold">NIS</th>
                                        <th class="p-3 font-semibold">Nama Siswa</th>
                                        <th class="p-3 font-semibold">Kelas</th>
                                        <th class="p-3 font-semibold text-center">Total Hadir</th>
                                        <th class="p-3 font-semibold text-center">Total Terlambat</th>
                                        <th class="p-3 font-semibold text-center">Total Pulang Cepat</th>
                                        <th class="p-3 font-semibold text-center">Total Izin/Cuti</th>
                                        <th class="p-3 font-semibold text-center rounded-r-xl text-rose-700 font-extrabold">Total Alpa (Bolos)</th>
                                    </tr>
                                </thead>
                                <tbody id="reportSemesterTableBody" class="divide-y divide-slate-100"></tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- SETTINGS TAB -->
            <div id="tab-settings" class="tab-content space-y-6">
                <div class="bg-white/90 backdrop-blur-md p-6 rounded-2xl shadow-sm border border-emerald-100/80 space-y-6">
                    <div class="pb-4 border-b border-emerald-100/80">
                        <h2 class="text-xl font-bold text-slate-800">Pengaturan Identitas, Logo, Jam Sekolah, & WhatsApp</h2>
                        <p class="text-xs text-slate-500">Konfigurasi data lengkap lembaga, logo sekolah, rentang jam absensi, dan saklar terpusat WhatsApp</p>
                    </div>

                    <form onsubmit="window.saveSettings(event)" class="space-y-6">
                        <div class="bg-emerald-50/70 p-5 rounded-2xl border border-emerald-200 space-y-3">
                            <div class="flex items-center justify-between">
                                <div class="space-y-0.5">
                                    <h3 class="text-sm font-bold text-emerald-900 flex items-center gap-2">
                                        <i class="fa-brands fa-whatsapp text-emerald-600 text-base"></i> Master Fitur WhatsApp Ortu
                                    </h3>
                                    <p class="text-xs text-slate-600">Aktifkan atau nonaktifkan seluruh notifikasi WhatsApp ke orang tua secara global.</p>
                                </div>
                                <label class="relative inline-flex items-center cursor-pointer">
                                    <input type="checkbox" id="settingWaEnabled" onchange="window.toggleWaSettingsUI()" class="sr-only peer">
                                    <div class="w-11 h-6 bg-slate-300 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-slate-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-emerald-600"></div>
                                </label>
                            </div>
                            <div id="waStatusAlert" class="text-[11px] font-semibold px-3 py-1.5 rounded-xl transition-all"></div>
                        </div>

                        <div class="bg-slate-50 p-5 rounded-2xl border border-emerald-100 space-y-4">
                            <h3 class="text-sm font-bold text-emerald-900 flex items-center gap-2">
                                <i class="fa-solid fa-image text-emerald-600"></i> Logo Resmi Lembaga / Sekolah
                            </h3>
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-6 items-center">
                                <div class="bg-emerald-900/90 p-4 rounded-2xl border border-amber-400/40 text-center space-y-2 shadow-md flex flex-col items-center justify-center">
                                    <span class="text-[10px] font-bold text-amber-300 uppercase tracking-wider">Pratinjau Logo</span>
                                    <div class="w-20 h-20 bg-white/10 backdrop-blur-md p-2 rounded-xl border border-white/20 flex items-center justify-center shadow-inner">
                                        <img id="settingLogoPreview" src="https://placehold.co/100x100/064e3b/ffffff?text=LOGO" alt="Logo Preview" class="max-w-full max-h-full object-contain">
                                    </div>
                                    <button type="button" onclick="window.clearSchoolLogo()" class="bg-rose-500/20 text-rose-200 border border-rose-400/30 px-2.5 py-1 rounded-lg text-[10px] font-bold hover:bg-rose-500 hover:text-white transition-all">
                                        <i class="fa-solid fa-trash mr-1"></i>Hapus Logo
                                    </button>
                                </div>
                                <div class="md:col-span-2 space-y-3">
                                    <div>
                                        <label class="block text-xs font-semibold text-slate-700 mb-1">Upload File Logo (Galeri/Perangkat):</label>
                                        <label class="w-full border-2 border-dashed border-emerald-300 bg-white hover:bg-emerald-50/50 p-3 rounded-xl flex items-center justify-center space-x-2 cursor-pointer transition-all">
                                            <i class="fa-solid fa-cloud-arrow-up text-emerald-600"></i>
                                            <span class="text-xs font-semibold text-slate-700">Pilih Gambar Logo (PNG / JPG)</span>
                                            <input type="file" accept="image/*" onchange="window.handleSettingLogoUpload(event)" class="hidden">
                                        </label>
                                    </div>
                                    <div>
                                        <label class="block text-xs font-semibold text-slate-700 mb-1">Atau Gunakan Link URL Logo:</label>
                                        <input type="text" id="settingSchoolLogo" placeholder="https://domain.com/logo-sekolah.png" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-medium">
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="bg-slate-50 p-5 rounded-2xl border border-emerald-100 space-y-4">
                            <h3 class="text-sm font-bold text-emerald-900 flex items-center gap-2">
                                <i class="fa-solid fa-school text-emerald-600"></i> Identitas Lengkap Lembaga
                            </h3>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                <div class="sm:col-span-2">
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Nama Resmi Sekolah / Lembaga:</label>
                                    <input type="text" id="settingSchoolName" required placeholder="Contoh: SMA NEGERI 1 UNGGUL" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-medium">
                                </div>
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">NPSN (Nomor Pokok Sekolah Nasional):</label>
                                    <input type="text" id="settingSchoolNpsn" placeholder="Contoh: 10801234" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-mono">
                                </div>
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Akreditasi Lembaga:</label>
                                    <select id="settingSchoolAccreditation" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3 py-2.5 font-medium focus:outline-none focus:border-emerald-500">
                                        <option value="A (Sangat Baik)">A (Sangat Baik)</option>
                                        <option value="B (Baik)">B (Baik)</option>
                                        <option value="C (Cukup)">C (Cukup)</option>
                                        <option value="Belum Terakreditasi">Belum Terakreditasi</option>
                                    </select>
                                </div>
                                <div class="sm:col-span-2">
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Alamat Lengkap Sekolah:</label>
                                    <input type="text" id="settingSchoolAddress" placeholder="Jalan, RT/RW, Kelurahan, Kecamatan" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-medium">
                                </div>
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Kabupaten / Kota & Provinsi:</label>
                                    <input type="text" id="settingSchoolCity" placeholder="Contoh: Jakarta Selatan, DKI Jakarta" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-medium">
                                </div>
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">No. Telepon / Kontak Resmi Lembaga:</label>
                                    <input type="text" id="settingSchoolPhone" placeholder="Contoh: (021) 7654321 / 08123456789" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-mono">
                                </div>
                            </div>
                        </div>

                        <!-- PENGATURAN JAM ABSENSI LENGKAP -->
                        <div class="bg-slate-50 p-5 rounded-2xl border border-emerald-100 space-y-4">
                            <h3 class="text-sm font-bold text-emerald-900 flex items-center gap-2">
                                <i class="fa-solid fa-clock text-emerald-600"></i> Pengaturan Jam Absensi Siswa & WhatsApp
                            </h3>
                            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Jam Mulai Bisa Absen Masuk:</label>
                                    <input type="time" id="settingTimeStartIn" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-medium">
                                    <p class="text-[10px] text-teal-700 mt-1 font-medium">*Sebelum jam ini, siswa belum bisa absen</p>
                                </div>
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Jam Terhitung Terlambat (Batas Tepat Waktu):</label>
                                    <input type="time" id="settingTimeLateLimit" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-medium">
                                    <p class="text-[10px] text-emerald-700 mt-1 font-medium">*Di atas jam ini terhitung Terlambat</p>
                                </div>
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Batas Jam Pulang Cepat:</label>
                                    <input type="time" id="settingTimeEarly" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-medium">
                                    <p class="text-[10px] text-amber-700 mt-1 font-medium">*Min. absen pulang cepat</p>
                                </div>
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Jam Pulang Normal:</label>
                                    <input type="time" id="settingTimeOut" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-medium">
                                    <p class="text-[10px] text-slate-500 mt-1 font-medium">*Jam kepulangan sekolah</p>
                                </div>
                            </div>
                            <div id="waTemplateContainer" class="pt-2">
                                <label class="block text-xs font-semibold text-slate-700 mb-1">Format Template Pesan WhatsApp:</label>
                                <textarea id="settingWaTemplate" rows="3" class="w-full bg-white border border-slate-200 text-xs rounded-xl p-3 focus:outline-none focus:border-emerald-500 font-medium">Yth. Orang Tua/Wali dari {nama} ({kelas}),\n\nInformasi Kehadiran Siswa:\nStatus: {status}\nWaktu: {waktu}\n\nTerima kasih.\n{sekolah}</textarea>
                                <p class="text-[10px] text-slate-400 mt-1">Gunakan tag: {nama}, {nis}, {kelas}, {ttl}, {status}, {waktu}, {sekolah}</p>
                            </div>
                        </div>

                        <div class="flex justify-end">
                            <button type="submit" class="bg-gradient-to-r from-emerald-500 to-teal-600 text-white px-8 py-3 rounded-xl text-xs font-bold shadow-md hover:brightness-105 transition-all flex items-center space-x-2">
                                <i class="fa-solid fa-floppy-disk text-sm"></i><span>Simpan Semua Pengaturan</span>
                            </button>
                        </div>
                    </form>

                    <div class="pt-6 border-t border-emerald-100 flex flex-wrap gap-3">
                        <button onclick="window.exportDatabase()" class="bg-teal-50 text-teal-700 border border-teal-200 px-4 py-2.5 rounded-xl text-xs font-semibold hover:bg-teal-100 transition-all">
                            <i class="fa-solid fa-download mr-1.5"></i> Backup Database (JSON)
                        </button>
                        <label class="bg-emerald-50 text-emerald-700 border border-emerald-200 px-4 py-2.5 rounded-xl text-xs font-semibold hover:bg-emerald-100 transition-all cursor-pointer">
                            <i class="fa-solid fa-upload mr-1.5"></i> Restore Database
                            <input type="file" accept=".json" onchange="window.importDatabase(event)" class="hidden">
                        </label>
                        <button onclick="window.resetDatabase()" class="bg-rose-50 text-rose-600 border border-rose-200 px-4 py-2.5 rounded-xl text-xs font-semibold hover:bg-rose-100 transition-all">
                            <i class="fa-solid fa-trash mr-1.5"></i> Reset Semua Data
                        </button>
                    </div>
                </div>
            </div>

        </section>
    </main>

    <!-- MODAL: ADD/EDIT STUDENT -->
    <div id="studentModal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-xs z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-2xl shadow-xl max-w-lg w-full p-6 space-y-4 border border-emerald-100 max-h-[90vh] overflow-y-auto">
            <div class="flex justify-between items-center pb-3 border-b border-slate-100">
                <h3 id="studentModalTitle" class="text-base font-bold text-slate-800">Edit Data Siswa & Foto</h3>
                <button onclick="window.closeStudentModal()" class="text-slate-400 hover:text-slate-600 text-sm"><i class="fa-solid fa-xmark"></i></button>
            </div>
            
            <form onsubmit="window.saveStudentForm(event)" class="space-y-4">
                <input type="hidden" id="editStudentOriginalNIS">
                
                <div class="bg-slate-50 p-4 rounded-2xl border border-emerald-100 space-y-3">
                    <span class="block text-xs font-bold text-emerald-900 flex items-center gap-1.5">
                        <i class="fa-solid fa-image text-emerald-600"></i> Pasfoto Resmi Siswa
                    </span>
                    <div class="flex flex-col sm:flex-row items-center gap-4">
                        <div class="w-24 h-32 bg-slate-900 rounded-xl overflow-hidden border-2 border-emerald-500/50 flex-shrink-0 flex items-center justify-center shadow-sm relative">
                            <img id="modalPhotoPreview" src="https://placehold.co/140x180/064e3b/ffffff?text=FOTO" alt="Foto Siswa" class="w-full h-full object-cover">
                        </div>
                        <div class="space-y-2.5 w-full">
                            <div>
                                <label class="block text-[11px] font-semibold text-slate-600 mb-1">Unggah File Foto (Galeri/HP/PC):</label>
                                <label class="w-full border border-dashed border-emerald-400 bg-white hover:bg-emerald-50 p-2.5 rounded-xl flex items-center justify-center gap-2 cursor-pointer transition-all">
                                    <i class="fa-solid fa-cloud-arrow-up text-emerald-600 text-xs"></i>
                                    <span class="text-xs font-semibold text-slate-700">Pilih Foto Siswa</span>
                                    <input type="file" accept="image/*" onchange="window.handleModalPhotoUpload(event)" class="hidden">
                                </label>
                            </div>
                            <div>
                                <label class="block text-[11px] font-semibold text-slate-600 mb-1">Atau Link / URL Gambar Foto:</label>
                                <input type="text" id="modalPhoto" oninput="window.updateModalPhotoPreviewFromUrl()" placeholder="https://domain.com/foto.jpg" class="w-full bg-white border border-slate-200 text-xs rounded-xl px-3 py-2 focus:outline-none focus:border-emerald-500">
                            </div>
                            <div class="flex justify-between items-center pt-1">
                                <span id="modalPhotoStatusBadge" class="text-[10px] font-bold px-2.5 py-0.5 rounded-full bg-amber-100 text-amber-800">Belum Ada Foto</span>
                                <button type="button" onclick="window.clearModalStudentPhoto()" class="text-rose-600 hover:text-rose-800 text-[11px] font-bold">
                                    <i class="fa-solid fa-trash mr-1"></i>Hapus Foto
                                </button>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">NIS:</label>
                        <input type="text" id="modalNIS" required class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-mono">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">NISN:</label>
                        <input type="text" id="modalNISN" required class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-mono">
                    </div>
                </div>
                <div>
                    <label class="block text-xs font-semibold text-slate-600 mb-1">Nama Lengkap Siswa:</label>
                    <input type="text" id="modalName" required class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500">
                </div>
                <div>
                    <label class="block text-xs font-semibold text-slate-600 mb-1">Tempat, Tanggal Lahir (TTL):</label>
                    <input type="text" id="modalTTL" placeholder="Contoh: Jakarta, 12 Mei 2008" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500">
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">Kelas:</label>
                        <input type="text" id="modalClass" required placeholder="Contoh: X IPA 1" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">No. WA Ortu:</label>
                        <input type="text" id="modalPhone" required placeholder="628123456789" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 focus:outline-none focus:border-emerald-500 font-mono">
                    </div>
                </div>
                
                <div class="pt-3 flex justify-end space-x-2 border-t border-slate-100">
                    <button type="button" onclick="window.closeStudentModal()" class="bg-slate-100 text-slate-600 px-4 py-2.5 rounded-xl text-xs font-semibold">Batal</button>
                    <button type="submit" class="bg-gradient-to-r from-emerald-500 to-teal-600 text-white px-6 py-2.5 rounded-xl text-xs font-bold shadow hover:brightness-105 transition-all">Simpan Data & Foto</button>
                </div>
            </form>
        </div>
    </div>

    <!-- MODAL: EDIT ATTENDANCE LOG HARI INI -->
    <div id="attendanceModal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-xs z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-2xl shadow-xl max-w-sm w-full p-6 space-y-4 border border-emerald-100">
            <div class="flex justify-between items-center pb-3 border-b border-slate-100">
                <h3 class="text-base font-bold text-slate-800">Edit Log Absensi Hari Ini</h3>
                <button onclick="window.closeAttendanceModal()" class="text-slate-400 hover:text-slate-600 text-sm"><i class="fa-solid fa-xmark"></i></button>
            </div>
            <form onsubmit="window.saveEditedAttendance(event)" class="space-y-4">
                <input type="hidden" id="editLogNis">
                <input type="hidden" id="editLogDate">
                <div>
                    <label class="block text-xs font-semibold text-slate-600 mb-1">Nama Siswa:</label>
                    <input type="text" id="editLogStudentName" disabled class="w-full bg-slate-100 border border-slate-200 text-xs rounded-xl px-3.5 py-2.5 font-bold text-slate-700">
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">Jam Masuk:</label>
                        <input type="time" id="editLogTimeIn" required class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3 py-2 font-medium">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">Status Masuk:</label>
                        <select id="editLogStatusIn" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3 py-2 font-medium">
                            <option value="Hadir">Hadir</option>
                            <option value="Terlambat">Terlambat</option>
                            <option value="Izin">Izin</option>
                            <option value="Sakit">Sakit</option>
                            <option value="Cuti">Cuti</option>
                            <option value="Alpa">Alpa</option>
                        </select>
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">Jam Pulang:</label>
                        <input type="time" id="editLogTimeOut" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3 py-2 font-medium">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">Status Pulang:</label>
                        <select id="editLogStatusOut" class="w-full bg-slate-50 border border-slate-200 text-xs rounded-xl px-3 py-2 font-medium">
                            <option value="">-</option>
                            <option value="Pulang">Pulang</option>
                            <option value="Pulang Cepat">Pulang Cepat</option>
                        </select>
                    </div>
                </div>
                <div class="pt-3 flex justify-end space-x-2 border-t border-slate-100">
                    <button type="button" onclick="window.closeAttendanceModal()" class="bg-slate-100 text-slate-600 px-4 py-2 rounded-xl text-xs font-semibold">Batal</button>
                    <button type="submit" class="bg-emerald-600 text-white px-5 py-2 rounded-xl text-xs font-bold shadow">Simpan Perubahan</button>
                </div>
            </form>
        </div>
    </div>

    <!-- MODAL: BULK IMPORT -->
    <div id="bulkModal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-xs z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-2xl shadow-xl max-w-md w-full p-6 space-y-4 border border-emerald-100">
            <div class="flex justify-between items-center pb-3 border-b border-slate-100">
                <h3 class="text-base font-bold text-slate-800">Import Massal Data Siswa</h3>
                <button onclick="window.closeBulkModal()" class="text-slate-400 hover:text-slate-600 text-sm"><i class="fa-solid fa-xmark"></i></button>
            </div>
            <div class="space-y-3">
                <p class="text-xs text-slate-600">Upload file Excel (.xlsx / .csv) atau gunakan Template & Input Data Kolom.</p>
                <div class="p-4 bg-emerald-50 rounded-xl border border-emerald-200 text-xs text-emerald-800 space-y-1">
                    <p class="font-bold">Format Kolom Excel:</p>
                    <p class="font-mono text-[11px]">NIS | NISN | Nama Siswa | Tempat Tanggal Lahir | Kelas | No WA Ortu | URL Foto</p>
                </div>
                <div class="pt-2 flex justify-end">
                    <button onclick="window.closeBulkModal()" class="bg-emerald-600 text-white px-4 py-2 rounded-xl text-xs font-semibold">Tutup</button>
                </div>
            </div>
        </div>
    </div>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        let db = {
            schoolName: "SMA NEGERI 1 UNGGUL",
            schoolNpsn: "10801234",
            schoolAccreditation: "A (Sangat Baik)",
            schoolAddress: "Jl. Pendidikan No. 45",
            schoolCity: "Jakarta Selatan, DKI Jakarta",
            schoolPhone: "(021) 7654321",
            schoolLogo: "", 
            timeStartIn: "06:00",
            timeLateLimit: "07:15",
            timeEarly: "13:00", 
            timeOut: "15:00",
            waEnabled: true,
            waTemplate: "Yth. Orang Tua/Wali dari {nama} ({kelas}),\n\nInformasi Kehadiran Siswa:\nStatus: {status}\nWaktu: {waktu}\n\nTerima kasih.\n{sekolah}",
            students: [
                { nis: "1001", nisn: "0051234567", name: "AHMAD SYARIFUDIN", ttl: "Jakarta, 12 Mei 2008", kelas: "X IPA 1", phone: "6281234567890", photo: "" },
                { nis: "1002", nisn: "0051234568", name: "SITI AMINAH", ttl: "Bandung, 20 Agustus 2008", kelas: "X IPA 1", phone: "6281234567891", photo: "" },
                { nis: "1003", nisn: "0051234569", name: "BUDI SANTOSO", ttl: "Surabaya, 05 Januari 2008", kelas: "X IPS 1", phone: "6281234567892", photo: "" }
            ],
            attendance: [],
            leaves: []
        };

        let html5QrCode = null;
        let isHardwareScannerActive = false;
        let tempModalPhotoData = "";
        let activeReportSubTab = 'daily';

        let gridRowsData = [
            { nis: "1004", nisn: "0051234570", name: "DEWI LESTARI", ttl: "Semarang, 14 November 2007", kelas: "XI IPA 2", phone: "6281234567893", photo: "" },
            { nis: "1005", nisn: "0051234571", name: "RIVAI KURNIAWAN", ttl: "Medan, 02 Maret 2007", kelas: "XI IPS 2", phone: "6281234567894", photo: "" }
        ];

        document.addEventListener("DOMContentLoaded", () => {
            checkLoginState();
            loadFromLocalStorage();
            startLiveClock();
            initGridRows();
            renderStudentsTable();
            populateClassDropdowns();
            populateLeaveStudentDropdown();
            renderLeaveTable();
            updateGeneratorStudentList();
            renderTodayLog();
            initReportDefaults();
            renderReports();
            loadSettingsToUI();
            initHardwareScannerListener();
            updateScannerWaUI();
        });

        function startLiveClock() {
            function updateClock() {
                const now = new Date();
                
                const optionsDate = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
                const dateString = now.toLocaleDateString('id-ID', optionsDate);

                const h = now.getHours();
                const m = now.getMinutes();
                const s = now.getSeconds();

                const hoursStr = String(h).padStart(2, '0');
                const minutesStr = String(m).padStart(2, '0');
                const secondsStr = String(s).padStart(2, '0');
                const timeString = `${hoursStr}:${minutesStr}:${secondsStr}`;

                const headerClockEl = document.getElementById("headerClock");
                if (headerClockEl) headerClockEl.innerText = `${dateString} | ${timeString}`;

                const liveDateEl = document.getElementById("liveClockDate");
                const liveTimeEl = document.getElementById("liveClockTime");
                if (liveDateEl) liveDateEl.innerText = dateString;
                if (liveTimeEl) liveTimeEl.innerText = timeString;

                const secDeg = (s / 60) * 360;
                const minDeg = ((m + s / 60) / 60) * 360;
                const hourDeg = (((h % 12) + m / 60) / 12) * 360;

                const secHand = document.getElementById("wallClockSecond");
                const minHand = document.getElementById("wallClockMinute");
                const hourHand = document.getElementById("wallClockHour");

                if (secHand) secHand.style.transform = `rotate(${secDeg}deg)`;
                if (minHand) minHand.style.transform = `rotate(${minDeg}deg)`;
                if (hourHand) hourHand.style.transform = `rotate(${hourDeg}deg)`;

                const schoolEl = document.getElementById("navSchoolName");
                if (schoolEl) schoolEl.innerText = db.schoolName;
            }

            updateClock();
            setInterval(updateClock, 1000);
        }

        function timeToMinutes(timeStr) {
            if (!timeStr) return 0;
            const parts = timeStr.split(':');
            return parseInt(parts[0], 10) * 60 + parseInt(parts[1], 10);
        }

        function checkLoginState() {
            const isLogged = sessionStorage.getItem("barcode_is_logged_in");
            const overlay = document.getElementById("loginOverlay");
            if (isLogged === "true") {
                if (overlay) overlay.classList.add("hidden");
            } else {
                if (overlay) overlay.classList.remove("hidden");
            }
        }

        window.handleLogin = function(e) {
            e.preventDefault();
            const user = document.getElementById("loginUsername").value.trim();
            const pass = document.getElementById("loginPassword").value.trim();

            if (user === "admin" && pass === "admin123") {
                sessionStorage.setItem("barcode_is_logged_in", "true");
                checkLoginState();
            } else {
                alert("Username atau Password salah! (Default: admin / admin123)");
            }
        };

        window.handleLogout = function() {
            if (confirm("Apakah Anda ingin keluar dari aplikasi?")) {
                sessionStorage.removeItem("barcode_is_logged_in");
                checkLoginState();
                document.getElementById("loginUsername").value = "";
                document.getElementById("loginPassword").value = "";
            }
        };

        function loadFromLocalStorage() {
            const saved = localStorage.getItem("barcode_attendance_db_v5_1");
            if (saved) {
                try { db = JSON.parse(saved); } catch(e) { console.error(e); }
            }
            if (!db.leaves) db.leaves = [];
            if (!db.schoolLogo) db.schoolLogo = "";
            if (!db.schoolNpsn) db.schoolNpsn = "";
            if (!db.schoolAccreditation) db.schoolAccreditation = "A (Sangat Baik)";
            if (!db.schoolAddress) db.schoolAddress = "";
            if (!db.schoolCity) db.schoolCity = "";
            if (!db.schoolPhone) db.schoolPhone = "";
            if (!db.timeStartIn) db.timeStartIn = "06:00";
            if (!db.timeLateLimit) db.timeLateLimit = "07:15";
            if (!db.timeEarly) db.timeEarly = "13:00";
            if (db.waEnabled === undefined) db.waEnabled = true;
        }

        function saveToLocalStorage() {
            localStorage.setItem("barcode_attendance_db_v5_1", JSON.stringify(db));
        }

        function updateScannerWaUI() {
            const toggle = document.getElementById("autoWhatsappToggle");
            if (!toggle) return;

            if (db.waEnabled) {
                toggle.disabled = false;
                toggle.parentElement.classList.remove("opacity-50", "cursor-not-allowed");
            } else {
                toggle.checked = false;
                toggle.disabled = true;
                toggle.parentElement.classList.add("opacity-50", "cursor-not-allowed");
            }
        }

        window.switchTab = function(tabId) {
            document.querySelectorAll(".tab-content").forEach(el => el.classList.remove("active"));
            document.querySelectorAll(".tab-btn").forEach(btn => {
                btn.className = "tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all text-slate-600 hover:bg-emerald-50 hover:text-emerald-700";
            });

            const targetContent = document.getElementById("tab-" + tabId);
            if (targetContent) targetContent.classList.add("active");

            const targetBtn = document.getElementById("btn-" + tabId);
            if (targetBtn) {
                targetBtn.className = "tab-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-medium transition-all bg-gradient-to-r from-emerald-500 to-teal-600 text-white shadow-md shadow-emerald-200/50 font-semibold";
            }

            if (tabId === 'generator') previewCard();
            else if (tabId === 'students') renderStudentsTable();
            else if (tabId === 'settings') loadSettingsToUI();
            else if (tabId === 'reports') renderReports();
            else if (tabId === 'leave-entry') { populateLeaveStudentDropdown(); renderLeaveTable(); }
            else if (tabId === 'scanner') {
                updateScannerWaUI();
                if (isHardwareScannerActive) document.getElementById("hardwareScannerInput").focus();
            }
        };

        window.toggleHardwareScannerMode = function() {
            isHardwareScannerActive = !isHardwareScannerActive;
            const btn = document.getElementById("btnHardwareToggle");
            const statusText = document.getElementById("hardwareStatusText");
            const hwInput = document.getElementById("hardwareScannerInput");

            if (isHardwareScannerActive) {
                btn.innerHTML = `<i class="fa-solid fa-circle-check mr-1.5"></i><span>Scanner Hardware Aktif</span>`;
                btn.className = "bg-emerald-800 text-white px-4 py-2 rounded-xl text-xs font-bold shadow transition-all";
                statusText.innerText = "Status: Terhubung & Siaga. Silakan tembak kartu dengan alat scanner USB/Wireless.";
                hwInput.focus();
            } else {
                btn.innerHTML = `<i class="fa-solid fa-plug mr-1.5"></i><span>Aktifkan Fokus Scanner</span>`;
                btn.className = "bg-white text-teal-700 px-4 py-2 rounded-xl text-xs font-bold shadow hover:bg-emerald-50 transition-all";
                statusText.innerText = "Status: Standby (Klik tombol untuk menghubungkan kembali scanner fisik)";
            }
        };

        function initHardwareScannerListener() {
            const hwInput = document.getElementById("hardwareScannerInput");
            if (!hwInput) return;

            document.addEventListener("click", () => {
                if (isHardwareScannerActive && document.getElementById("tab-scanner").classList.contains("active")) {
                    hwInput.focus();
                }
            });

            hwInput.addEventListener("keypress", function(e) {
                if (e.key === "Enter") {
                    e.preventDefault();
                    const scannedCode = hwInput.value.trim();
                    if (scannedCode) {
                        processScannedNIS(scannedCode);
                        hwInput.value = "";
                    }
                }
            });
        }

        function populateClassDropdowns() {
            const classes = [...new Set(db.students.map(s => s.kelas))].filter(Boolean).sort();
            const filterSel = document.getElementById("filterClassSelect");
            const genSel = document.getElementById("genClassSelect");
            [filterSel, genSel].forEach(sel => {
                if (!sel) return;
                const currentVal = sel.value;
                sel.innerHTML = '<option value="">Semua Kelas</option>';
                classes.forEach(c => sel.innerHTML += `<option value="${c}">${c}</option>`);
                sel.value = currentVal;
            });
        }

        function populateLeaveStudentDropdown() {
            const sel = document.getElementById("leaveStudentSelect");
            if (!sel) return;
            sel.innerHTML = '<option value="">-- Pilih Siswa --</option>';
            db.students.forEach(s => {
                sel.innerHTML += `<option value="${s.nis}">${s.nis} - ${s.name} (${s.kelas})</option>`;
            });
        }

        window.saveLeaveEntry = function(e) {
            e.preventDefault();
            const nis = document.getElementById("leaveStudentSelect").value;
            const type = document.getElementById("leaveTypeSelect").value;
            const startDate = document.getElementById("leaveStartDate").value;
            const endDate = document.getElementById("leaveEndDate").value;
            const reason = document.getElementById("leaveReason").value.trim();

            if (!nis || !startDate || !endDate) { alert("Lengkapi data izin!"); return; }
            if (startDate > endDate) { alert("Tanggal mulai tidak boleh lebih besar dari tanggal selesai!"); return; }

            const student = db.students.find(s => s.nis === nis);
            if (!student) return;

            const leaveObj = { id: Date.now(), nis, type, startDate, endDate, reason };
            db.leaves.push(leaveObj);

            let cur = new Date(startDate);
            const end = new Date(endDate);
            while (cur <= end) {
                const dateStr = cur.toISOString().split('T')[0];
                let existing = db.attendance.find(a => a.nis === nis && a.date === dateStr);
                if (!existing) {
                    db.attendance.unshift({
                        date: dateStr,
                        nis: nis,
                        timeIn: '00:00',
                        timeOut: '00:00',
                        statusIn: type,
                        statusOut: type
                    });
                } else {
                    existing.statusIn = type;
                    existing.statusOut = type;
                }
                cur.setDate(cur.getDate() + 1);
            }

            saveToLocalStorage();
            renderLeaveTable();
            renderTodayLog();
            renderReports();

            if (db.waEnabled && confirm(`Izin/Cuti ${type} untuk ${student.name} tersimpan. Kirim WhatsApp ke Orang Tua?`)) {
                sendLeaveWhatsAppNotification(student, type, startDate, endDate, reason);
            }

            document.getElementById("leaveReason").value = "";
            document.getElementById("leaveStartDate").value = "";
            document.getElementById("leaveEndDate").value = "";
        };

        function sendLeaveWhatsAppNotification(student, type, startDate, endDate, reason) {
            if (!db.waEnabled) {
                alert("Fitur WhatsApp Ortu saat ini sedang dinonaktifkan di Pengaturan.");
                return;
            }
            let period = startDate === endDate ? startDate : `${startDate} s/d ${endDate}`;
            let msg = `Yth. Orang Tua/Wali dari ${student.name} (${student.kelas}),\n\nPemberitahuan Keterangan Siswa:\nStatus: ${type}\nPeriode: ${period}\nAlasan: ${reason || '-'}\n\nTerima kasih.\n${db.schoolName}`;
            let phone = student.phone ? student.phone.replace(/[^0-9]/g, '') : '';
            if (phone.startsWith('0')) phone = '62' + phone.substring(1);
            if (phone) window.open(`https://wa.me/${phone}?text=${encodeURIComponent(msg)}`, '_blank');
        }

        function renderLeaveTable() {
            const tbody = document.getElementById("leaveTableBody");
            if (!tbody) return;
            if (db.leaves.length === 0) {
                tbody.innerHTML = `<tr><td colspan="8" class="text-center py-6 text-slate-400">Belum ada pengajuan izin/cuti.</td></tr>`;
                return;
            }

            tbody.innerHTML = "";
            db.leaves.forEach((l, idx) => {
                const s = db.students.find(item => item.nis === l.nis) || { name: 'Unknown', kelas: '-' };
                const period = l.startDate === l.endDate ? l.startDate : `${l.startDate} s/d ${l.endDate}`;
                tbody.innerHTML += `
                    <tr class="hover:bg-slate-50">
                        <td class="p-3 font-bold text-slate-500">${idx + 1}</td>
                        <td class="p-3 font-mono font-bold">${l.nis}</td>
                        <td class="p-3 font-bold text-slate-800">${s.name}</td>
                        <td class="p-3"><span class="bg-emerald-50 text-emerald-700 px-2 py-0.5 rounded font-semibold">${s.kelas}</span></td>
                        <td class="p-3"><span class="bg-amber-100 text-amber-800 font-bold px-2.5 py-1 rounded-full text-[10px] uppercase">${l.type}</span></td>
                        <td class="p-3 font-mono text-slate-700">${period}</td>
                        <td class="p-3 text-slate-600">${l.reason || '-'}</td>
                        <td class="p-3 text-right space-x-1">
                            <button onclick="window.resendLeaveWA('${l.id}')" class="bg-emerald-50 text-emerald-700 border border-emerald-200 px-2.5 py-1.5 rounded-xl text-xs font-semibold hover:bg-emerald-100"><i class="fa-brands fa-whatsapp"></i></button>
                            <button onclick="window.deleteLeave('${l.id}')" class="bg-rose-50 text-rose-600 border border-rose-200 px-2.5 py-1.5 rounded-xl text-xs font-semibold hover:bg-rose-100"><i class="fa-solid fa-trash"></i></button>
                        </td>
                    </tr>
                `;
            });
        }

        window.resendLeaveWA = function(id) {
            const l = db.leaves.find(item => item.id == id);
            if (!l) return;
            const s = db.students.find(item => item.nis === l.nis);
            if (s) sendLeaveWhatsAppNotification(s, l.type, l.startDate, l.endDate, l.reason);
        };

        window.deleteLeave = function(id) {
            if (confirm("Hapus catatan izin/cuti ini?")) {
                db.leaves = db.leaves.filter(item => item.id != id);
                saveToLocalStorage();
                renderLeaveTable();
                renderReports();
            }
        };

        window.startScanner = function() {
            const placeholder = document.getElementById("scannerPlaceholder");
            if (placeholder) placeholder.style.display = "none";

            if (!html5QrCode) html5QrCode = new Html5Qrcode("reader");
            html5QrCode.start(
                { facingMode: "environment" },
                { fps: 10, qrbox: { width: 220, height: 220 } },
                (decodedText) => { processScannedNIS(decodedText.trim()); },
                (errorMessage) => {}
            ).catch(err => { alert("Gagal mengaktifkan kamera: " + err); });
        };

        window.stopScanner = function() {
            if (html5QrCode) {
                html5QrCode.stop().then(() => {
                    html5QrCode.clear();
                    html5QrCode = null;
                    const placeholder = document.getElementById("scannerPlaceholder");
                    if (placeholder) placeholder.style.display = "flex";
                }).catch(err => console.log(err));
            }
        };

        window.handleManualScan = function(e) {
            e.preventDefault();
            const input = document.getElementById("manualNIS");
            const nis = input.value.trim();
            if (nis) { processScannedNIS(nis); input.value = ""; }
        };

        function processScannedNIS(nis) {
            const student = db.students.find(s => s.nis === nis || s.nisn === nis);
            if (!student) {
                alert("Siswa dengan NIS/NISN '" + nis + "' tidak ditemukan!");
                if (isHardwareScannerActive) document.getElementById("hardwareScannerInput").focus();
                return;
            }

            const now = new Date();
            const dateStr = now.toISOString().split('T')[0];
            const hours = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            const seconds = String(now.getSeconds()).padStart(2, '0');
            const timeStr = `${hours}:${minutes}`;
            const timeFullStr = `${hours}:${minutes}:${seconds}`;
            const mode = document.getElementById("scanModeSelect").value;

            const nowMin = timeToMinutes(timeStr);
            const timeStartInMin = timeToMinutes(db.timeStartIn || "06:00");
            const timeLateLimitMin = timeToMinutes(db.timeLateLimit || "07:15");
            const timeEarlyMin = timeToMinutes(db.timeEarly || "13:00");
            const timeOutMin = timeToMinutes(db.timeOut || "15:00");

            let existing = db.attendance.find(a => a.nis === student.nis && a.date === dateStr);
            let actionType = "";
            let statusText = "";

            if (mode === "AUTO") {
                if (!existing) {
                    // Cek Jam Mulai Absen Masuk
                    if (nowMin < timeStartInMin) {
                        alert(`PERINGATAN: Absen masuk untuk ${student.name} belum dibuka!\n\nJam mulai absen masuk ditetapkan pukul ${db.timeStartIn}.`);
                        if (isHardwareScannerActive) document.getElementById("hardwareScannerInput").focus();
                        return;
                    }

                    // Tentukan Hadir atau Terlambat berdasarkan Batas Tepat Waktu (timeLateLimit)
                    statusText = (nowMin > timeLateLimitMin) ? "Terlambat" : "Hadir";
                    db.attendance.unshift({
                        date: dateStr,
                        nis: student.nis,
                        timeIn: timeStr,
                        timeOut: null,
                        statusIn: statusText,
                        statusOut: null
                    });
                    actionType = `MASUK (${statusText.toUpperCase()})`;
                } else if (!existing.timeOut) {
                    if (nowMin < timeEarlyMin) {
                        alert(`PERINGATAN: ${student.name} sudah absen Masuk pukul ${existing.timeIn}.\n\nAbsen Pulang belum dibuka! Jam Absen Pulang Cepat baru dibuka pukul ${db.timeEarly}.`);
                        if (isHardwareScannerActive) document.getElementById("hardwareScannerInput").focus();
                        return;
                    }

                    if (nowMin >= timeEarlyMin && nowMin < timeOutMin) {
                        statusText = "Pulang Cepat";
                    } else {
                        statusText = "Pulang";
                    }

                    existing.timeOut = timeStr;
                    existing.statusOut = statusText;
                    actionType = `PULANG (${statusText.toUpperCase()})`;
                } else {
                    alert(`${student.name} sudah melakukan absensi Masuk (${existing.timeIn}) dan Pulang (${existing.timeOut}) hari ini.`);
                    if (isHardwareScannerActive) document.getElementById("hardwareScannerInput").focus();
                    return;
                }
            } else {
                statusText = mode;
                if (!existing) {
                    db.attendance.unshift({
                        date: dateStr,
                        nis: student.nis,
                        timeIn: timeStr,
                        timeOut: null,
                        statusIn: statusText,
                        statusOut: null
                    });
                } else {
                    if (mode === "Pulang Cepat" || mode === "Pulang") {
                        if (nowMin < timeEarlyMin) {
                            if (!confirm(`Saat ini belum mencapai Jam Pulang Cepat (${db.timeEarly}). Apakah Anda yakin ingin memproses manual absen pulang siswa ini?`)) {
                                if (isHardwareScannerActive) document.getElementById("hardwareScannerInput").focus();
                                return;
                            }
                        }
                        existing.timeOut = timeStr;
                        existing.statusOut = mode;
                    } else {
                        existing.statusIn = statusText;
                    }
                }
                actionType = `MANUAL (${statusText.toUpperCase()})`;
            }

            saveToLocalStorage();
            renderTodayLog();
            renderReports();

            document.getElementById("lastScanName").innerText = student.name;
            document.getElementById("lastScanClass").innerText = `Kelas: ${student.kelas} | TTL: ${student.ttl || '-'}`;
            document.getElementById("lastScanNIS").innerText = `${student.nis} / ${student.nisn || '-'}`;
            document.getElementById("lastScanTime").innerText = `${timeFullStr} WIB`;

            const badge = document.getElementById("lastScanBadge");
            badge.innerText = `BERHASIL: ${actionType}`;
            badge.className = "inline-block py-1 px-3.5 rounded-full text-xs font-extrabold uppercase tracking-wider shadow " + 
                (statusText === 'Hadir' || statusText === 'Pulang' ? 'bg-emerald-400 text-slate-900' : 'bg-amber-400 text-slate-900');

            const avatar = document.getElementById("lastScanAvatar");
            if (student.photo) avatar.innerHTML = `<img src="${student.photo}" class="w-full h-full object-cover">`;
            else avatar.innerHTML = `<i class="fa-solid fa-user text-5xl text-emerald-400"></i>`;

            const resultCard = document.getElementById("scanResultCardContainer");
            resultCard.classList.remove("scan-success-anim");
            void resultCard.offsetWidth;
            resultCard.classList.add("scan-success-anim");

            const autoWaToggle = document.getElementById("autoWhatsappToggle");
            const autoWa = autoWaToggle ? autoWaToggle.checked : false;
            if (db.waEnabled && autoWa && student.phone) {
                sendWhatsAppNotification(student, actionType, timeFullStr);
            }

            if (isHardwareScannerActive) {
                document.getElementById("hardwareScannerInput").focus();
            }
        }

        function sendWhatsAppNotification(student, actionType, timeStr) {
            if (!db.waEnabled || !student.phone) return;
            let msg = db.waTemplate
                .replace(/{nama}/g, student.name)
                .replace(/{nis}/g, student.nis)
                .replace(/{kelas}/g, student.kelas)
                .replace(/{ttl}/g, student.ttl || '-')
                .replace(/{status}/g, actionType)
                .replace(/{waktu}/g, timeStr)
                .replace(/{sekolah}/g, db.schoolName);
            
            let phone = student.phone.replace(/[^0-9]/g, '');
            if (phone.startsWith('0')) phone = '62' + phone.substring(1);
            if (phone) window.open(`https://wa.me/${phone}?text=${encodeURIComponent(msg)}`, '_blank');
        }

        function renderTodayLog() {
            const todayStr = new Date().toISOString().split('T')[0];
            const tbody = document.getElementById("todayLogTableBody");
            const todayLogs = db.attendance.filter(a => a.date === todayStr);
            
            document.getElementById("todayCountBadge").innerText = todayLogs.length + " Siswa";

            if (todayLogs.length === 0) {
                tbody.innerHTML = `<tr><td colspan="8" class="text-center py-8 text-slate-400">Belum ada absensi tercatat hari ini.</td></tr>`;
                return;
            }

            tbody.innerHTML = "";
            todayLogs.forEach(log => {
                const student = db.students.find(s => s.nis === log.nis) || { name: "Unknown", kelas: "-" };
                const badgeIn = log.statusIn === 'Hadir' ? 'bg-emerald-100 text-emerald-800' : (log.statusIn === 'Terlambat' ? 'bg-amber-100 text-amber-800' : 'bg-blue-100 text-blue-800');
                const badgeOut = log.statusOut === 'Pulang' ? 'bg-emerald-100 text-emerald-800' : (log.statusOut === 'Pulang Cepat' ? 'bg-rose-100 text-rose-800' : 'bg-slate-100 text-slate-600');

                tbody.innerHTML += `
                    <tr class="hover:bg-slate-50/80 transition-all">
                        <td class="p-3 font-mono font-medium">${log.timeIn || '-'}</td>
                        <td class="p-3 font-mono font-bold">${log.nis}</td>
                        <td class="p-3 font-bold text-slate-800">${student.name}</td>
                        <td class="p-3"><span class="bg-emerald-50 text-emerald-700 px-2.5 py-1 rounded-lg font-semibold">${student.kelas}</span></td>
                        <td class="p-3"><span class="px-2.5 py-1 rounded-full text-[10px] font-bold uppercase ${badgeIn}">${log.statusIn}</span></td>
                        <td class="p-3 font-mono">${log.timeOut || '<span class="text-amber-500 italic">Belum Pulang</span>'}</td>
                        <td class="p-3"><span class="px-2.5 py-1 rounded-full text-[10px] font-bold uppercase ${badgeOut}">${log.statusOut || '-'}</span></td>
                        <td class="p-3 text-right space-x-1">
                            <button onclick="window.openEditAttendanceModal('${log.nis}', '${log.date}')" title="Edit Log" class="bg-teal-50 text-teal-700 border border-teal-200 px-2.5 py-1.5 rounded-xl text-xs font-semibold hover:bg-teal-100"><i class="fa-solid fa-pen-to-square"></i></button>
                            <button onclick="window.deleteAttendanceLog('${log.nis}', '${log.date}')" title="Hapus Log" class="bg-rose-50 text-rose-600 border border-rose-200 px-2.5 py-1.5 rounded-xl text-xs font-semibold hover:bg-rose-100"><i class="fa-solid fa-trash"></i></button>
                        </td>
                    </tr>
                `;
            });
        }

        window.openEditAttendanceModal = function(nis, date) {
            const log = db.attendance.find(a => a.nis === nis && a.date === date);
            const student = db.students.find(s => s.nis === nis);
            if (!log || !student) return;

            document.getElementById("editLogNis").value = nis;
            document.getElementById("editLogDate").value = date;
            document.getElementById("editLogStudentName").value = `${student.name} (${student.kelas})`;
            document.getElementById("editLogTimeIn").value = log.timeIn || "";
            document.getElementById("editLogStatusIn").value = log.statusIn || "Hadir";
            document.getElementById("editLogTimeOut").value = log.timeOut || "";
            document.getElementById("editLogStatusOut").value = log.statusOut || "";

            document.getElementById("attendanceModal").classList.remove("hidden");
        };

        window.closeAttendanceModal = function() {
            document.getElementById("attendanceModal").classList.add("hidden");
        };

        window.saveEditedAttendance = function(e) {
            e.preventDefault();
            const nis = document.getElementById("editLogNis").value;
            const date = document.getElementById("editLogDate").value;
            const timeIn = document.getElementById("editLogTimeIn").value;
            const statusIn = document.getElementById("editLogStatusIn").value;
            const timeOut = document.getElementById("editLogTimeOut").value;
            const statusOut = document.getElementById("editLogStatusOut").value;

            const idx = db.attendance.findIndex(a => a.nis === nis && a.date === date);
            if (idx >= 0) {
                db.attendance[idx].timeIn = timeIn;
                db.attendance[idx].statusIn = statusIn;
                db.attendance[idx].timeOut = timeOut;
                db.attendance[idx].statusOut = statusOut;

                saveToLocalStorage();
                closeAttendanceModal();
                renderTodayLog();
                renderReports();
                alert("Log absensi berhasil diperbarui!");
            }
        };

        window.deleteAttendanceLog = function(nis, date) {
            if (confirm("Hapus catatan absensi siswa ini untuk hari ini?")) {
                db.attendance = db.attendance.filter(a => !(a.nis === nis && a.date === date));
                saveToLocalStorage();
                renderTodayLog();
                renderReports();
            }
        };

        window.renderStudentsTable = function() {
            const keyword = document.getElementById("searchStudentInput").value.toLowerCase();
            const filterClass = document.getElementById("filterClassSelect").value;
            const tbody = document.getElementById("studentsTableBody");

            let filtered = db.students.filter(s => {
                const matchKey = s.name.toLowerCase().includes(keyword) || 
                                 s.nis.toLowerCase().includes(keyword) || 
                                 s.nisn.toLowerCase().includes(keyword) || 
                                 (s.ttl && s.ttl.toLowerCase().includes(keyword)) ||
                                 s.phone.includes(keyword);
                const matchClass = filterClass ? s.kelas === filterClass : true;
                return matchKey && matchClass;
            });

            if (filtered.length === 0) {
                tbody.innerHTML = `<tr><td colspan="8" class="text-center py-8 text-slate-400">Tidak ada data siswa.</td></tr>`;
                return;
            }

            tbody.innerHTML = "";
            filtered.forEach(s => {
                const photoHtml = s.photo ? 
                    `<img src="${s.photo}" class="w-10 h-10 object-cover rounded-xl border border-emerald-300 shadow-xs">` : 
                    `<div class="w-10 h-10 bg-slate-100 rounded-xl flex items-center justify-center text-slate-400 font-bold border border-slate-200"><i class="fa-solid fa-user text-sm"></i></div>`;
                
                const photoBadge = s.photo ? 
                    `<span class="inline-flex items-center gap-1 bg-emerald-100 text-emerald-800 px-2.5 py-1 rounded-full text-[10px] font-bold"><i class="fa-solid fa-circle-check text-emerald-600"></i> Sudah Unggah Foto</span>` : 
                    `<span class="inline-flex items-center gap-1 bg-amber-100 text-amber-800 px-2.5 py-1 rounded-full text-[10px] font-bold"><i class="fa-solid fa-triangle-exclamation text-amber-600"></i> Belum Ada Foto</span>`;

                tbody.innerHTML += `
                    <tr class="hover:bg-slate-50/80 transition-all">
                        <td class="p-3">${photoHtml}</td>
                        <td class="p-3">${photoBadge}</td>
                        <td class="p-3 font-mono"><b class="text-slate-800">${s.nis}</b> / <span class="text-slate-500">${s.nisn || '-'}</span></td>
                        <td class="p-3 font-bold text-slate-800">${s.name}</td>
                        <td class="p-3 text-slate-600 font-medium">${s.ttl || '-'}</td>
                        <td class="p-3"><span class="bg-emerald-50 text-emerald-700 px-2.5 py-1 rounded-lg font-semibold">${s.kelas}</span></td>
                        <td class="p-3 font-mono">${s.phone}</td>
                        <td class="p-3 text-right space-x-1">
                            <button onclick="window.editStudent('${s.nis}')" title="Edit Data & Foto Siswa" class="bg-teal-50 text-teal-700 border border-teal-200 px-3 py-1.5 rounded-xl text-xs font-semibold hover:bg-teal-100 transition-all"><i class="fa-solid fa-user-pen mr-1"></i> Edit</button>
                            <button onclick="window.deleteStudent('${s.nis}')" title="Hapus Siswa" class="bg-rose-50 text-rose-600 border border-rose-200 px-2.5 py-1.5 rounded-xl text-xs font-semibold hover:bg-rose-100 transition-all"><i class="fa-solid fa-trash"></i></button>
                        </td>
                    </tr>
                `;
            });
        };

        window.handleModalPhotoUpload = function(e) {
            const file = e.target.files[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(evt) {
                tempModalPhotoData = evt.target.result;
                document.getElementById("modalPhoto").value = evt.target.result;
                updateModalPhotoPreview();
            };
            reader.readAsDataURL(file);
        };

        window.updateModalPhotoPreviewFromUrl = function() {
            tempModalPhotoData = document.getElementById("modalPhoto").value.trim();
            updateModalPhotoPreview();
        };

        function updateModalPhotoPreview() {
            const img = document.getElementById("modalPhotoPreview");
            const badge = document.getElementById("modalPhotoStatusBadge");
            const photoVal = tempModalPhotoData;

            if (photoVal) {
                img.src = photoVal;
                badge.innerText = "Sudah Unggah Foto";
                badge.className = "text-[10px] font-bold px-2.5 py-0.5 rounded-full bg-emerald-100 text-emerald-800";
            } else {
                img.src = "https://placehold.co/140x180/064e3b/ffffff?text=FOTO";
                badge.innerText = "Belum Ada Foto";
                badge.className = "text-[10px] font-bold px-2.5 py-0.5 rounded-full bg-amber-100 text-amber-800";
            }
        }

        window.clearModalStudentPhoto = function() {
            tempModalPhotoData = "";
            document.getElementById("modalPhoto").value = "";
            updateModalPhotoPreview();
        };

        window.openStudentModal = function(nis = null) {
            document.getElementById("studentModal").classList.remove("hidden");
            if (nis) {
                const s = db.students.find(item => item.nis === nis);
                if (s) {
                    document.getElementById("studentModalTitle").innerText = "Edit Data Siswa & Foto";
                    document.getElementById("editStudentOriginalNIS").value = s.nis;
                    document.getElementById("modalNIS").value = s.nis;
                    document.getElementById("modalNISN").value = s.nisn || "";
                    document.getElementById("modalName").value = s.name;
                    document.getElementById("modalTTL").value = s.ttl || "";
                    document.getElementById("modalClass").value = s.kelas;
                    document.getElementById("modalPhone").value = s.phone;
                    document.getElementById("modalPhoto").value = s.photo || "";
                    tempModalPhotoData = s.photo || "";
                    updateModalPhotoPreview();
                }
            } else {
                document.getElementById("studentModalTitle").innerText = "Tambah Siswa Baru";
                document.getElementById("editStudentOriginalNIS").value = "";
                document.getElementById("modalNIS").value = "";
                document.getElementById("modalNISN").value = "";
                document.getElementById("modalName").value = "";
                document.getElementById("modalTTL").value = "";
                document.getElementById("modalClass").value = "";
                document.getElementById("modalPhone").value = "";
                document.getElementById("modalPhoto").value = "";
                tempModalPhotoData = "";
                updateModalPhotoPreview();
            }
        };

        window.closeStudentModal = function() { document.getElementById("studentModal").classList.add("hidden"); };

        window.saveStudentForm = function(e) {
            e.preventDefault();
            const origNIS = document.getElementById("editStudentOriginalNIS").value;
            const nis = document.getElementById("modalNIS").value.trim();
            const nisn = document.getElementById("modalNISN").value.trim();
            const name = document.getElementById("modalName").value.trim().toUpperCase();
            const ttl = document.getElementById("modalTTL").value.trim();
            const kelas = document.getElementById("modalClass").value.trim();
            const phone = document.getElementById("modalPhone").value.trim();
            const photo = tempModalPhotoData || document.getElementById("modalPhoto").value.trim();

            if (origNIS) {
                const idx = db.students.findIndex(s => s.nis === origNIS);
                if (idx >= 0) db.students[idx] = { nis, nisn, name, ttl, kelas, phone, photo };
            } else {
                if (db.students.some(s => s.nis === nis)) { alert("NIS sudah terdaftar!"); return; }
                db.students.push({ nis, nisn, name, ttl, kelas, phone, photo });
            }

            saveToLocalStorage();
            closeStudentModal();
            renderStudentsTable();
            populateClassDropdowns();
            populateLeaveStudentDropdown();
            updateGeneratorStudentList();
            alert(`Data siswa ${name} berhasil disimpan!`);
        };

        window.editStudent = function(nis) { openStudentModal(nis); };
        window.deleteStudent = function(nis) {
            if (confirm("Hapus data siswa ini?")) {
                db.students = db.students.filter(s => s.nis !== nis);
                saveToLocalStorage();
                renderStudentsTable();
                populateClassDropdowns();
                populateLeaveStudentDropdown();
                updateGeneratorStudentList();
            }
        };

        window.openBulkModal = function() { document.getElementById("bulkModal").classList.remove("hidden"); };
        window.closeBulkModal = function() { document.getElementById("bulkModal").classList.add("hidden"); };

        function initGridRows() {
            const tbody = document.getElementById("gridTableBody");
            if (!tbody) return;
            tbody.innerHTML = "";
            gridRowsData.forEach((row, idx) => addRowToGridDOM(idx + 1, row));
        }

        function addRowToGridDOM(no, data = {}) {
            const tbody = document.getElementById("gridTableBody");
            const tr = document.createElement("tr");
            tr.className = "grid-row hover:bg-slate-50";
            tr.innerHTML = `
                <td class="p-2 text-center font-bold text-slate-500 row-no">${no}</td>
                <td class="p-2"><input type="text" value="${data.nis || ''}" class="grid-nis w-full bg-slate-50 border border-slate-200 rounded-lg px-2 py-1.5 font-mono text-xs"></td>
                <td class="p-2"><input type="text" value="${data.nisn || ''}" class="grid-nisn w-full bg-slate-50 border border-slate-200 rounded-lg px-2 py-1.5 font-mono text-xs"></td>
                <td class="p-2"><input type="text" value="${data.name || ''}" class="grid-name w-full bg-slate-50 border border-slate-200 rounded-lg px-2 py-1.5 text-xs"></td>
                <td class="p-2"><input type="text" value="${data.ttl || ''}" placeholder="Jakarta, 12 Mei 2008" class="grid-ttl w-full bg-slate-50 border border-slate-200 rounded-lg px-2 py-1.5 text-xs"></td>
                <td class="p-2"><input type="text" value="${data.kelas || ''}" class="grid-class w-full bg-slate-50 border border-slate-200 rounded-lg px-2 py-1.5 text-xs"></td>
                <td class="p-2"><input type="text" value="${data.phone || ''}" class="grid-phone w-full bg-slate-50 border border-slate-200 rounded-lg px-2 py-1.5 font-mono text-xs"></td>
                <td class="p-2"><input type="text" value="${data.photo || ''}" class="grid-photo w-full bg-slate-50 border border-slate-200 rounded-lg px-2 py-1.5 text-xs"></td>
                <td class="p-2 text-center"><button type="button" onclick="window.removeGridRow(this)" class="text-rose-500 hover:text-rose-700 p-1"><i class="fa-solid fa-trash text-xs"></i></button></td>
            `;
            tbody.appendChild(tr);
        }

        window.addGridRow = function() { addRowToGridDOM(document.querySelectorAll(".grid-row").length + 1); };
        window.removeGridRow = function(btn) {
            btn.closest("tr").remove();
            document.querySelectorAll(".grid-row").forEach((tr, idx) => tr.querySelector(".row-no").innerText = idx + 1);
        };
        window.clearGridRows = function() { document.getElementById("gridTableBody").innerHTML = ""; window.addGridRow(); };

        window.saveGridData = function() {
            const rows = document.querySelectorAll(".grid-row");
            let addedCount = 0;
            rows.forEach(tr => {
                const nis = tr.querySelector(".grid-nis").value.trim();
                const nisn = tr.querySelector(".grid-nisn").value.trim();
                const name = tr.querySelector(".grid-name").value.trim().toUpperCase();
                const ttl = tr.querySelector(".grid-ttl").value.trim();
                const kelas = tr.querySelector(".grid-class").value.trim();
                const phone = tr.querySelector(".grid-phone").value.trim();
                const photo = tr.querySelector(".grid-photo").value.trim();
                if (nis && name) {
                    const existingIdx = db.students.findIndex(s => s.nis === nis);
                    if (existingIdx >= 0) db.students[existingIdx] = { nis, nisn, name, ttl, kelas, phone, photo };
                    else { db.students.push({ nis, nisn, name, ttl, kelas, phone, photo }); addedCount++; }
                }
            });
            saveToLocalStorage();
            renderStudentsTable();
            populateClassDropdowns();
            populateLeaveStudentDropdown();
            updateGeneratorStudentList();
            alert(`Berhasil! ${addedCount} data siswa disimpan.`);
            window.switchTab('students');
        };

        window.downloadExcelTemplate = function() {
            const wsData = [
                ["NIS", "NISN", "Nama Siswa", "Tempat Tanggal Lahir", "Kelas", "No WA Ortu", "URL Foto"],
                ["1001", "0051234567", "AHMAD SYARIFUDIN", "Jakarta, 12 Mei 2008", "X IPA 1", "6281234567890", ""]
            ];
            const wb = XLSX.utils.book_new();
            XLSX.utils.book_append_sheet(wb, XLSX.utils.aoa_to_sheet(wsData), "Template");
            XLSX.writeFile(wb, "Template_Siswa.xlsx");
        };

        window.handleExcelFileUpload = function(e) {
            const file = e.target.files[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(evt) {
                try {
                    const data = new Uint8Array(evt.target.result);
                    const workbook = XLSX.read(data, { type: 'array' });
                    const json = XLSX.utils.sheet_to_json(workbook.Sheets[workbook.SheetNames[0]], { header: 1 });
                    gridRowsData = [];
                    for (let i = 1; i < json.length; i++) {
                        const row = json[i];
                        if (row && row[0]) {
                            gridRowsData.push({ 
                                nis: String(row[0]), 
                                nisn: String(row[1]||''), 
                                name: String(row[2]||''), 
                                ttl: String(row[3]||''), 
                                kelas: String(row[4]||''), 
                                phone: String(row[5]||''), 
                                photo: String(row[6]||'') 
                            });
                        }
                    }
                    if (gridRowsData.length === 0) gridRowsData.push({});
                    initGridRows();
                    alert("File berhasil diunggah ke grid!");
                    window.switchTab('template-entry');
                } catch(err) { alert("Error Excel: " + err); }
            };
            reader.readAsArrayBuffer(file);
        };

        // GENERATOR TAB
        window.updateGeneratorStudentList = function() {
            const classSel = document.getElementById("genClassSelect");
            const studentSel = document.getElementById("genStudentSelect");
            const selectedClass = classSel ? classSel.value : "";
            const classes = [...new Set(db.students.map(s => s.kelas))].filter(Boolean).sort();
            if (classSel && classSel.options.length <= 1) {
                classSel.innerHTML = '<option value="">Semua Kelas</option>';
                classes.forEach(c => classSel.innerHTML += `<option value="${c}">${c}</option>`);
                classSel.value = selectedClass;
            }
            let filtered = db.students.filter(s => selectedClass ? s.kelas === selectedClass : true);
            studentSel.innerHTML = "";
            filtered.forEach(s => studentSel.innerHTML += `<option value="${s.nis}">${s.nis} - ${s.name} (${s.kelas})</option>`);
            previewCard();
        };

        window.previewCard = function() {
            const studentSel = document.getElementById("genStudentSelect");
            if (!studentSel || !studentSel.value) return;
            const student = db.students.find(s => s.nis === studentSel.value);
            if (!student) return;

            document.getElementById("cardSchoolName").innerText = db.schoolName;
            document.getElementById("cardSchoolLogo").src = db.schoolLogo || `https://placehold.co/100x100/064e3b/ffffff?text=LOGO`;
            document.getElementById("cardStudentName").innerText = student.name;
            document.getElementById("cardStudentClass").innerText = student.kelas;
            document.getElementById("cardStudentNIS").innerText = student.nis;
            document.getElementById("cardStudentNISN").innerText = student.nisn || '-';
            document.getElementById("cardStudentTTL").innerText = student.ttl || '-';
            document.getElementById("cardStudentPhoto").src = student.photo || `https://placehold.co/140x180/064e3b/ffffff?text=${encodeURIComponent(student.name.split(' ')[0])}`;

            const qrContainer = document.getElementById("qrcodeElement");
            qrContainer.innerHTML = "";
            new QRCode(qrContainer, { text: student.nis, width: 70, height: 70, colorDark: "#064e3b", colorLight: "#ffffff", correctLevel: QRCode.CorrectLevel.H });
        };

        window.printCard = function() {
            const cardHtml = document.getElementById("cardPreviewContainer").outerHTML;
            const win = window.open('', '_blank', 'width=500,height=700');
            win.document.write(`
                <html>
                <head>
                    <title>Cetak Kartu Tunggal (7 cm x 9 cm)</title>
                    <script src="https://cdn.tailwindcss.com"><\/script>
                    <style>
                        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&family=Playfair+Display:wght@700&display=swap');
                        * { -webkit-print-color-adjust: exact !important; print-color-adjust: exact !important; box-sizing: border-box !important; }
                        @page { size: 7cm 9cm; margin: 0; }
                        body { font-family: 'Plus Jakarta Sans', sans-serif; background: white; margin: 0; padding: 0; width: 7cm; height: 9cm; display: flex; justify-content: center; align-items: center; }
                        .font-card-title { font-family: 'Playfair Display', serif; }
                        .card-precise-dim { width: 5.5cm !important; height: 8.7cm !important; box-sizing: border-box !important; }
                        .card-emerald-bg { background-color: #064e3b !important; background-image: radial-gradient(rgba(245,158,11,0.18) 1px, transparent 0) !important; background-size: 8px 8px !important; }
                    </style>
                </head>
                <body>
                    ${cardHtml}
                    <script>
                        setTimeout(() => { window.print(); window.close(); }, 700);
                    <\/script>
                </body>
                </html>
            `);
            win.document.close();
        };

        window.printBulkCards = function() {
            const classSel = document.getElementById("genClassSelect").value;
            let targetStudents = db.students.filter(s => classSel ? s.kelas === classSel : true);
            if (targetStudents.length === 0) { alert("Tidak ada data siswa untuk dicetak!"); return; }

            const logoUrl = db.schoolLogo || `https://placehold.co/100x100/064e3b/ffffff?text=LOGO`;

            let pagesHtml = "";
            for (let p = 0; p < targetStudents.length; p += 9) {
                const chunk = targetStudents.slice(p, p + 9);
                let cardsInPageHtml = "";

                chunk.forEach((student, indexInChunk) => {
                    const globalIdx = p + indexInChunk;
                    const photoUrl = student.photo || `https://placehold.co/140x180/064e3b/ffffff?text=${encodeURIComponent(student.name.split(' ')[0])}`;
                    
                    cardsInPageHtml += `
                        <div class="card-precise-dim card-emerald-bg text-slate-100 rounded-2xl shadow-sm relative overflow-hidden flex flex-col justify-between p-3 border border-amber-400/40">
                            <div class="absolute inset-1.5 border border-amber-400/30 rounded-xl pointer-events-none z-20"></div>
                            
                            <div class="relative z-10 pt-0.5 border-b border-amber-400/20 pb-1 flex items-center justify-center space-x-2">
                                <div class="w-6 h-6 flex items-center justify-center overflow-hidden flex-shrink-0">
                                    <img src="${logoUrl}" alt="Logo" class="w-full h-full object-contain">
                                </div>
                                <div class="text-center">
                                    <h4 class="font-bold text-[8.5px] leading-tight uppercase text-amber-300 font-card-title line-clamp-1">${db.schoolName}</h4>
                                    <p class="text-[5px] text-emerald-200/80 tracking-widest uppercase font-semibold">KARTU TANDA PELAJAR RESMI</p>
                                </div>
                            </div>
                            
                            <div class="flex flex-col items-center text-center space-y-1 my-auto relative z-10">
                                <div class="p-0.5 rounded-xl bg-gradient-to-tr from-amber-500 via-amber-200 to-amber-500 shadow-sm">
                                    <div class="w-22 h-28 bg-slate-900 rounded-lg overflow-hidden flex items-center justify-center border border-emerald-800">
                                        <img src="${photoUrl}" class="w-full h-full object-cover">
                                    </div>
                                </div>
                                <div class="w-full space-y-0.5 px-0.5">
                                    <h3 class="font-extrabold text-[9.5px] text-white line-clamp-1 uppercase">${student.name}</h3>
                                    <div class="inline-block bg-amber-400/20 border border-amber-400/40 text-amber-300 font-bold text-[6.5px] px-2 py-0.2 rounded-full uppercase"><span>${student.kelas}</span></div>
                                    <div class="bg-emerald-950/90 rounded-lg py-1 px-2 text-[6.5px] font-mono space-y-0.5 border border-emerald-800/80 text-emerald-100 leading-none">
                                        <div class="flex justify-between"><span class="text-emerald-300/60">NIS:</span> <span class="font-bold text-amber-300">${student.nis}</span></div>
                                        <div class="flex justify-between"><span class="text-emerald-300/60">NISN:</span> <span class="font-bold text-white">${student.nisn || '-'}</span></div>
                                        <div class="flex justify-between border-t border-emerald-800/60 pt-0.5 text-[6px]"><span class="text-emerald-300/60">TTL:</span> <span class="font-semibold text-emerald-100 truncate max-w-[105px]">${student.ttl || '-'}</span></div>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="bg-emerald-950/90 rounded-xl p-1 flex flex-col items-center justify-center border border-amber-400/30 relative z-10">
                                <div class="bg-white p-0.5 rounded-lg border border-slate-200 flex items-center justify-center">
                                    <div id="bulk-qr-${globalIdx}" class="w-[70px] h-[70px]"></div>
                                </div>
                                <p class="text-[5px] font-bold text-amber-300 uppercase tracking-widest mt-0.5">VERIFIKASI ABSENSI</p>
                            </div>
                        </div>
                    `;
                });

                pagesHtml += `
                    <div class="a4-page">
                        <div class="grid-3x3">
                            ${cardsInPageHtml}
                        </div>
                    </div>
                `;
            }

            const win = window.open('', '_blank', 'width=1000,height=800');
            win.document.write(`
                <html>
                <head>
                    <title>Cetak Massal Kartu Pelajar A4 (5.5 x 8.7 cm)</title>
                    <script src="https://cdn.tailwindcss.com"><\/script>
                    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"><\/script>
                    <style>
                        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&family=Playfair+Display:wght@700&display=swap');
                        * { -webkit-print-color-adjust: exact !important; print-color-adjust: exact !important; box-sizing: border-box !important; }
                        body { font-family: 'Plus Jakarta Sans', sans-serif; background-color: #f1f5f9; margin: 0; padding: 0; }
                        .font-card-title { font-family: 'Playfair Display', serif; }
                        .a4-page { width: 210mm; height: 297mm; padding: 4mm 3mm; margin: 10px auto; background: white; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); box-sizing: border-box; page-break-after: always; break-after: page; display: flex; justify-content: center; align-items: center; }
                        .grid-3x3 { display: grid; grid-template-columns: repeat(3, 5.5cm); grid-template-rows: repeat(3, 8.7cm); gap: 4mm 4mm; justify-content: center; align-content: center; }
                        .card-precise-dim { width: 5.5cm !important; height: 8.7cm !important; box-sizing: border-box !important; }
                        .card-emerald-bg { background-color: #064e3b !important; background-image: radial-gradient(rgba(245,158,11,0.18) 1px, transparent 0) !important; background-size: 8px 8px !important; }
                        @media print {
                            @page { size: A4 portrait; margin: 0; }
                            body { background: white !important; }
                            .a4-page { margin: 0 !important; box-shadow: none !important; page-break-after: always !important; break-after: page !important; }
                        }
                    </style>
                </head>
                <body>
                    ${pagesHtml}
                    <script>
                        const targetData = ${JSON.stringify(targetStudents)};
                        targetData.forEach((s, i) => {
                            const container = document.getElementById('bulk-qr-' + i);
                            if (container) {
                                new QRCode(container, { text: s.nis, width: 70, height: 70, colorDark: "#064e3b", colorLight: "#ffffff", correctLevel: QRCode.CorrectLevel.H });
                            }
                        });
                        setTimeout(() => { window.print(); window.close(); }, 1200);
                    <\/script>
                </body>
                </html>
            `);
            win.document.close();
        };

        // REPORTS
        window.switchReportSubTab = function(subId) {
            activeReportSubTab = subId;
            document.querySelectorAll(".rep-sub-content").forEach(el => el.classList.add("hidden"));
            document.querySelectorAll(".rep-sub-tab").forEach(btn => btn.className = "rep-sub-tab px-4 py-2 rounded-xl text-xs font-bold transition-all bg-slate-100 text-slate-600 hover:bg-emerald-50");
            document.getElementById("rep-sub-" + subId).classList.remove("hidden");
            document.getElementById("btn-rep-" + subId).className = "rep-sub-tab px-4 py-2 rounded-xl text-xs font-bold transition-all bg-emerald-600 text-white shadow-sm";
            renderReports();
        };

        function initReportDefaults() {
            const today = new Date().toISOString().split('T')[0];
            const dateInput = document.getElementById("reportDailyDate");
            if (dateInput && !dateInput.value) dateInput.value = today;
            const monthInput = document.getElementById("reportMonthInput");
            if (monthInput && !monthInput.value) monthInput.value = today.substring(0, 7);
        }

        window.renderReports = function() {
            const dailyDate = document.getElementById("reportDailyDate").value;
            const dailyTbody = document.getElementById("reportDailyTableBody");
            dailyTbody.innerHTML = "";

            db.students.forEach((s, idx) => {
                const log = db.attendance.find(a => a.nis === s.nis && a.date === dailyDate);
                const masuk = log ? log.timeIn : '-';
                const pulang = log && log.timeOut ? log.timeOut : '<span class="text-amber-500">Belum</span>';
                const status = log ? `${log.statusIn}${log.statusOut ? ' & ' + log.statusOut : ''}` : 'Alpa';
                const badgeColor = status.includes('Terlambat') || status.includes('Cepat') || status.includes('Izin') || status.includes('Sakit') || status.includes('Cuti') ? 'bg-amber-100 text-amber-800' : 'bg-emerald-100 text-emerald-800';

                dailyTbody.innerHTML += `
                    <tr class="hover:bg-slate-50">
                        <td class="p-3 font-bold">${idx + 1}</td>
                        <td class="p-3 font-mono font-bold">${s.nis}</td>
                        <td class="p-3 font-bold text-slate-800">${s.name}</td>
                        <td class="p-3"><span class="bg-emerald-50 text-emerald-700 px-2 py-0.5 rounded">${s.kelas}</span></td>
                        <td class="p-3 font-mono">${masuk}</td>
                        <td class="p-3 font-mono">${pulang}</td>
                        <td class="p-3"><span class="px-2.5 py-1 rounded-full text-[10px] font-bold uppercase ${badgeColor}">${status}</span></td>
                    </tr>
                `;
            });

            // Monthly Report & Top 10 Bolos
            const monthStr = document.getElementById("reportMonthInput").value;
            let monthlyStudentStats = db.students.map(s => {
                let hadir = 0, terlambat = 0, pulangCepat = 0, leaveCount = 0, alpa = 0;
                if (monthStr) {
                    const logs = db.attendance.filter(a => a.nis === s.nis && a.date.startsWith(monthStr));
                    hadir = logs.filter(l => l.statusIn === 'Hadir').length;
                    terlambat = logs.filter(l => l.statusIn === 'Terlambat').length;
                    pulangCepat = logs.filter(l => l.statusOut === 'Pulang Cepat').length;
                    leaveCount = logs.filter(l => ['Izin', 'Sakit', 'Cuti'].includes(l.statusIn)).length;
                    alpa = logs.filter(l => l.statusIn === 'Alpa').length;
                }
                return { ...s, hadir, terlambat, pulangCepat, leaveCount, alpa };
            });

            monthlyStudentStats.sort((a, b) => b.alpa - a.alpa);

            const monthlyTbody = document.getElementById("reportMonthlyTableBody");
            monthlyTbody.innerHTML = "";
            monthlyStudentStats.forEach((s, idx) => {
                monthlyTbody.innerHTML += `
                    <tr class="hover:bg-slate-50">
                        <td class="p-3 font-bold">${idx + 1}</td>
                        <td class="p-3 font-mono font-bold">${s.nis}</td>
                        <td class="p-3 font-bold text-slate-800">${s.name}</td>
                        <td class="p-3"><span class="bg-emerald-50 text-emerald-700 px-2 py-0.5 rounded">${s.kelas}</span></td>
                        <td class="p-3 text-center font-bold text-emerald-700">${s.hadir}</td>
                        <td class="p-3 text-center font-bold text-amber-600">${s.terlambat}</td>
                        <td class="p-3 text-center font-bold text-rose-600">${s.pulangCepat}</td>
                        <td class="p-3 text-center font-bold text-teal-600">${s.leaveCount}</td>
                        <td class="p-3 text-center font-extrabold text-rose-700 text-sm">${s.alpa}</td>
                    </tr>
                `;
            });

            renderTopBolosChart('monthlyTopBolosChartContainer', monthlyStudentStats);

            // Semester Report & Top 10 Bolos
            const semester = document.getElementById("reportSemesterSelect").value;
            let semesterStudentStats = db.students.map(s => {
                let hadir = 0, terlambat = 0, pulangCepat = 0, leaveCount = 0, alpa = 0;
                db.attendance.forEach(l => {
                    if (l.nis === s.nis) {
                        const month = parseInt(l.date.split('-')[1]);
                        const isSem1 = (semester === '1' && month >= 7 && month <= 12);
                        const isSem2 = (semester === '2' && month >= 1 && month <= 6);
                        if (isSem1 || isSem2) {
                            if (l.statusIn === 'Hadir') hadir++;
                            if (l.statusIn === 'Terlambat') terlambat++;
                            if (l.statusOut === 'Pulang Cepat') pulangCepat++;
                            if (['Izin', 'Sakit', 'Cuti'].includes(l.statusIn)) leaveCount++;
                            if (l.statusIn === 'Alpa') alpa++;
                        }
                    }
                });
                return { ...s, hadir, terlambat, pulangCepat, leaveCount, alpa };
            });

            semesterStudentStats.sort((a, b) => b.alpa - a.alpa);

            const semesterTbody = document.getElementById("reportSemesterTableBody");
            semesterTbody.innerHTML = "";
            semesterStudentStats.forEach((s, idx) => {
                semesterTbody.innerHTML += `
                    <tr class="hover:bg-slate-50">
                        <td class="p-3 font-bold">${idx + 1}</td>
                        <td class="p-3 font-mono font-bold">${s.nis}</td>
                        <td class="p-3 font-bold text-slate-800">${s.name}</td>
                        <td class="p-3"><span class="bg-emerald-50 text-emerald-700 px-2 py-0.5 rounded">${s.kelas}</span></td>
                        <td class="p-3 text-center font-bold text-emerald-700">${s.hadir}</td>
                        <td class="p-3 text-center font-bold text-amber-600">${s.terlambat}</td>
                        <td class="p-3 text-center font-bold text-rose-600">${s.pulangCepat}</td>
                        <td class="p-3 text-center font-bold text-teal-600">${s.leaveCount}</td>
                        <td class="p-3 text-center font-extrabold text-rose-700 text-sm">${s.alpa}</td>
                    </tr>
                `;
            });

            renderTopBolosChart('semesterTopBolosChartContainer', semesterStudentStats);
        };

        function renderTopBolosChart(containerId, statsArray) {
            const container = document.getElementById(containerId);
            if (!container) return;

            const top10 = statsArray.slice(0, 10);
            const maxAlpa = Math.max(...top10.map(s => s.alpa), 1);

            if (top10.length === 0 || top10.every(s => s.alpa === 0)) {
                container.innerHTML = `<div class="text-center py-6 text-rose-200 text-xs italic">Belum ada catatan siswa bolos/alpa pada periode ini.</div>`;
                return;
            }

            container.innerHTML = "";
            top10.forEach((s, idx) => {
                const percentage = Math.round((s.alpa / maxAlpa) * 100);
                const rankColor = idx === 0 ? 'bg-amber-400 text-slate-900' : (idx === 1 ? 'bg-slate-300 text-slate-900' : (idx === 2 ? 'bg-amber-700 text-white' : 'bg-rose-900/80 text-rose-200'));

                container.innerHTML += `
                    <div class="space-y-1">
                        <div class="flex justify-between items-center text-xs">
                            <div class="flex items-center space-x-2">
                                <span class="w-5 h-5 rounded-full flex items-center justify-center font-bold text-[10px] ${rankColor}">${idx + 1}</span>
                                <span class="font-bold text-white truncate max-w-[200px] sm:max-w-xs">${s.name}</span>
                                <span class="bg-rose-950/80 border border-rose-700/50 text-rose-300 text-[10px] px-2 py-0.5 rounded font-semibold">${s.kelas}</span>
                            </div>
                            <span class="font-mono font-extrabold text-amber-300 text-xs">${s.alpa} Hari Alpa</span>
                        </div>
                        <div class="w-full bg-slate-950/80 rounded-full h-3 p-0.5 border border-rose-800/50 overflow-hidden shadow-inner">
                            <div class="bg-gradient-to-r from-rose-500 via-red-500 to-amber-500 h-full rounded-full transition-all duration-500 shadow-sm" style="width: ${Math.max(percentage, 6)}%;"></div>
                        </div>
                    </div>
                `;
            });
        }

        window.exportActiveReportToExcel = function() {
            const wb = XLSX.utils.book_new();
            let exportData = [];

            if (activeReportSubTab === 'daily') {
                const dailyDate = document.getElementById("reportDailyDate").value;
                exportData.push(["REKAPITULASI KEHADIRAN HARIAN SISWA"]);
                exportData.push([`Lembaga: ${db.schoolName}`]);
                exportData.push([`Tanggal: ${dailyDate}`]);
                exportData.push([]);

                let studentsByClass = {};
                db.students.forEach(s => {
                    const k = s.kelas || "Tanpa Kelas";
                    if (!studentsByClass[k]) studentsByClass[k] = [];
                    studentsByClass[k].push(s);
                });

                const sortedClasses = Object.keys(studentsByClass).sort();

                sortedClasses.forEach(kelas => {
                    exportData.push([`KELAS: ${kelas}`]);
                    exportData.push(["No", "NIS", "NISN", "Nama Siswa", "Kelas", "Waktu Masuk", "Waktu Pulang", "Status Kehadiran"]);

                    const classStudents = studentsByClass[kelas].sort((a,b) => a.name.localeCompare(b.name));
                    classStudents.forEach((s, idx) => {
                        const log = db.attendance.find(a => a.nis === s.nis && a.date === dailyDate);
                        const masuk = log ? log.timeIn : '-';
                        const pulang = log && log.timeOut ? log.timeOut : '-';
                        const status = log ? `${log.statusIn}${log.statusOut ? ' & ' + log.statusOut : ''}` : 'Alpa';
                        exportData.push([idx + 1, s.nis, s.nisn || '', s.name, s.kelas, masuk, pulang, status]);
                    });
                    exportData.push([]);
                });

                const ws = XLSX.utils.aoa_to_sheet(exportData);
                XLSX.utils.book_append_sheet(wb, ws, "Laporan Harian");
                XLSX.writeFile(wb, `Laporan_Harian_${dailyDate}.xlsx`);

            } else if (activeReportSubTab === 'monthly') {
                const monthStr = document.getElementById("reportMonthInput").value;
                exportData.push(["REKAPITULASI KEHADIRAN BULANAN SISWA PER KELAS"]);
                exportData.push([`Lembaga: ${db.schoolName}`]);
                exportData.push([`Periode Bulan: ${monthStr}`]);
                exportData.push([]);

                let studentsByClass = {};
                db.students.forEach(s => {
                    const k = s.kelas || "Tanpa Kelas";
                    if (!studentsByClass[k]) studentsByClass[k] = [];

                    const logs = db.attendance.filter(a => a.nis === s.nis && a.date.startsWith(monthStr));
                    const hadir = logs.filter(l => l.statusIn === 'Hadir').length;
                    const terlambat = logs.filter(l => l.statusIn === 'Terlambat').length;
                    const pulangCepat = logs.filter(l => l.statusOut === 'Pulang Cepat').length;
                    const leaveCount = logs.filter(l => ['Izin', 'Sakit', 'Cuti'].includes(l.statusIn)).length;
                    const alpa = logs.filter(l => l.statusIn === 'Alpa').length;

                    studentsByClass[k].push({ ...s, hadir, terlambat, pulangCepat, leaveCount, alpa });
                });

                const sortedClasses = Object.keys(studentsByClass).sort();

                let grandTotalHadir = 0, grandTotalTerlambat = 0, grandTotalPulangCepat = 0, grandTotalLeave = 0, grandTotalAlpa = 0;

                sortedClasses.forEach(kelas => {
                    exportData.push([`KELAS: ${kelas}`]);
                    exportData.push(["No", "NIS", "NISN", "Nama Siswa", "Kelas", "Hadir", "Terlambat", "Pulang Cepat", "Izin/Sakit/Cuti", "Alpa (Bolos)"]);

                    let classHadir = 0, classTerlambat = 0, classPulangCepat = 0, classLeave = 0, classAlpa = 0;

                    const classStudents = studentsByClass[kelas].sort((a,b) => a.name.localeCompare(b.name));
                    classStudents.forEach((s, idx) => {
                        exportData.push([idx + 1, s.nis, s.nisn || '', s.name, s.kelas, s.hadir, s.terlambat, s.pulangCepat, s.leaveCount, s.alpa]);
                        classHadir += s.hadir;
                        classTerlambat += s.terlambat;
                        classPulangCepat += s.pulangCepat;
                        classLeave += s.leaveCount;
                        classAlpa += s.alpa;
                    });

                    exportData.push(["", "", "", `TOTAL KELAS ${kelas}`, "", classHadir, classTerlambat, classPulangCepat, classLeave, classAlpa]);
                    exportData.push([]);

                    grandTotalHadir += classHadir;
                    grandTotalTerlambat += classTerlambat;
                    grandTotalPulangCepat += classPulangCepat;
                    grandTotalLeave += classLeave;
                    grandTotalAlpa += classAlpa;
                });

                exportData.push(["", "", "", "TOTAL KESELURUHAN SEKOLAH", "", grandTotalHadir, grandTotalTerlambat, grandTotalPulangCepat, grandTotalLeave, grandTotalAlpa]);

                const ws = XLSX.utils.aoa_to_sheet(exportData);
                XLSX.utils.book_append_sheet(wb, ws, "Laporan Bulanan");
                XLSX.writeFile(wb, `Laporan_Bulanan_${monthStr}.xlsx`);

            } else if (activeReportSubTab === 'semester') {
                const semester = document.getElementById("reportSemesterSelect").value;
                const semText = semester === '1' ? 'Semester Ganjil (Juli - Desember)' : 'Semester Genap (Januari - Juni)';
                
                exportData.push(["REKAPITULASI KEHADIRAN SEMESTER SISWA PER KELAS"]);
                exportData.push([`Lembaga: ${db.schoolName}`]);
                exportData.push([`Periode: ${semText}`]);
                exportData.push([]);

                let studentsByClass = {};
                db.students.forEach(s => {
                    const k = s.kelas || "Tanpa Kelas";
                    if (!studentsByClass[k]) studentsByClass[k] = [];

                    let hadir = 0, terlambat = 0, pulangCepat = 0, leaveCount = 0, alpa = 0;
                    db.attendance.forEach(l => {
                        if (l.nis === s.nis) {
                            const month = parseInt(l.date.split('-')[1]);
                            const isSem1 = (semester === '1' && month >= 7 && month <= 12);
                            const isSem2 = (semester === '2' && month >= 1 && month <= 6);
                            if (isSem1 || isSem2) {
                                if (l.statusIn === 'Hadir') hadir++;
                                if (l.statusIn === 'Terlambat') terlambat++;
                                if (l.statusOut === 'Pulang Cepat') pulangCepat++;
                                if (['Izin', 'Sakit', 'Cuti'].includes(l.statusIn)) leaveCount++;
                                if (l.statusIn === 'Alpa') alpa++;
                            }
                        }
                    });

                    studentsByClass[k].push({ ...s, hadir, terlambat, pulangCepat, leaveCount, alpa });
                });

                const sortedClasses = Object.keys(studentsByClass).sort();

                let grandTotalHadir = 0, grandTotalTerlambat = 0, grandTotalPulangCepat = 0, grandTotalLeave = 0, grandTotalAlpa = 0;

                sortedClasses.forEach(kelas => {
                    exportData.push([`KELAS: ${kelas}`]);
                    exportData.push(["No", "NIS", "NISN", "Nama Siswa", "Kelas", "Total Hadir", "Total Terlambat", "Total Pulang Cepat", "Total Izin/Cuti", "Total Alpa (Bolos)"]);

                    let classHadir = 0, classTerlambat = 0, classPulangCepat = 0, classLeave = 0, classAlpa = 0;

                    const classStudents = studentsByClass[kelas].sort((a,b) => a.name.localeCompare(b.name));
                    classStudents.forEach((s, idx) => {
                        exportData.push([idx + 1, s.nis, s.nisn || '', s.name, s.kelas, s.hadir, s.terlambat, s.pulangCepat, s.leaveCount, s.alpa]);
                        classHadir += s.hadir;
                        classTerlambat += s.terlambat;
                        classPulangCepat += s.pulangCepat;
                        classLeave += s.leaveCount;
                        classAlpa += s.alpa;
                    });

                    exportData.push(["", "", "", `TOTAL KELAS ${kelas}`, "", classHadir, classTerlambat, classPulangCepat, classLeave, classAlpa]);
                    exportData.push([]);

                    grandTotalHadir += classHadir;
                    grandTotalTerlambat += classTerlambat;
                    grandTotalPulangCepat += classPulangCepat;
                    grandTotalLeave += classLeave;
                    grandTotalAlpa += classAlpa;
                });

                exportData.push(["", "", "", "TOTAL KESELURUHAN SEKOLAH", "", grandTotalHadir, grandTotalTerlambat, grandTotalPulangCepat, grandTotalLeave, grandTotalAlpa]);

                const ws = XLSX.utils.aoa_to_sheet(exportData);
                XLSX.utils.book_append_sheet(wb, ws, "Laporan Semester");
                XLSX.writeFile(wb, `Laporan_Semester_${semester}.xlsx`);
            }
        };

        // SETTINGS LOGIC
        function loadSettingsToUI() {
            document.getElementById("settingSchoolName").value = db.schoolName || "";
            document.getElementById("settingSchoolNpsn").value = db.schoolNpsn || "";
            document.getElementById("settingSchoolAccreditation").value = db.schoolAccreditation || "A (Sangat Baik)";
            document.getElementById("settingSchoolAddress").value = db.schoolAddress || "";
            document.getElementById("settingSchoolCity").value = db.schoolCity || "";
            document.getElementById("settingSchoolPhone").value = db.schoolPhone || "";
            document.getElementById("settingSchoolLogo").value = db.schoolLogo || "";
            document.getElementById("settingTimeStartIn").value = db.timeStartIn || "06:00";
            document.getElementById("settingTimeLateLimit").value = db.timeLateLimit || "07:15";
            document.getElementById("settingTimeEarly").value = db.timeEarly || "13:00";
            document.getElementById("settingTimeOut").value = db.timeOut || "15:00";
            document.getElementById("settingWaEnabled").checked = db.waEnabled !== false;
            document.getElementById("settingWaTemplate").value = db.waTemplate || "";
            
            document.getElementById("infoTimeStartIn").innerText = db.timeStartIn || "06:00";
            document.getElementById("infoTimeLateLimit").innerText = db.timeLateLimit || "07:15";
            document.getElementById("infoTimeEarly").innerText = db.timeEarly || "13:00";
            document.getElementById("infoTimeOut").innerText = db.timeOut || "15:00";

            const previewImg = document.getElementById("settingLogoPreview");
            if (previewImg) {
                previewImg.src = db.schoolLogo || "https://placehold.co/100x100/064e3b/ffffff?text=LOGO";
            }

            toggleWaSettingsUI();
        }

        window.toggleWaSettingsUI = function() {
            const isChecked = document.getElementById("settingWaEnabled").checked;
            const alertBox = document.getElementById("waStatusAlert");
            const tplContainer = document.getElementById("waTemplateContainer");

            if (isChecked) {
                alertBox.innerText = "Status Fitur: AKTIF (Pengiriman notifikasi WhatsApp ke Orang Tua berjalan normal)";
                alertBox.className = "text-[11px] font-semibold px-3 py-1.5 rounded-xl bg-emerald-100 text-emerald-800 border border-emerald-200";
                if (tplContainer) tplContainer.classList.remove("opacity-50", "pointer-events-none");
            } else {
                alertBox.innerText = "Status Fitur: NONAKTIF (Seluruh pengiriman notifikasi WhatsApp ke Orang Tua dimatikan)";
                alertBox.className = "text-[11px] font-semibold px-3 py-1.5 rounded-xl bg-rose-100 text-rose-800 border border-rose-200";
                if (tplContainer) tplContainer.classList.add("opacity-50", "pointer-events-none");
            }
        };

        window.handleSettingLogoUpload = function(e) {
            const file = e.target.files[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(evt) {
                db.schoolLogo = evt.target.result;
                document.getElementById("settingSchoolLogo").value = evt.target.result;
                document.getElementById("settingLogoPreview").src = evt.target.result;
            };
            reader.readAsDataURL(file);
        };

        window.clearSchoolLogo = function() {
            if (confirm("Hapus logo sekolah?")) {
                db.schoolLogo = "";
                document.getElementById("settingSchoolLogo").value = "";
                document.getElementById("settingLogoPreview").src = "https://placehold.co/100x100/064e3b/ffffff?text=LOGO";
                saveToLocalStorage();
            }
        };

        window.saveSettings = function(e) {
            e.preventDefault();
            db.schoolName = document.getElementById("settingSchoolName").value.trim();
            db.schoolNpsn = document.getElementById("settingSchoolNpsn").value.trim();
            db.schoolAccreditation = document.getElementById("settingSchoolAccreditation").value;
            db.schoolAddress = document.getElementById("settingSchoolAddress").value.trim();
            db.schoolCity = document.getElementById("settingSchoolCity").value.trim();
            db.schoolPhone = document.getElementById("settingSchoolPhone").value.trim();
            db.schoolLogo = document.getElementById("settingSchoolLogo").value.trim();
            db.timeStartIn = document.getElementById("settingTimeStartIn").value;
            db.timeLateLimit = document.getElementById("settingTimeLateLimit").value;
            db.timeEarly = document.getElementById("settingTimeEarly").value;
            db.timeOut = document.getElementById("settingTimeOut").value;
            db.waEnabled = document.getElementById("settingWaEnabled").checked;
            db.waTemplate = document.getElementById("settingWaTemplate").value;

            saveToLocalStorage();
            loadSettingsToUI();
            updateScannerWaUI();
            alert("Pengaturan jam masuk, batas terlambat, dan identitas lembaga berhasil disimpan!");
        };

        window.exportDatabase = function() {
            const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(db, null, 2));
            const dl = document.createElement('a');
            dl.setAttribute("href", dataStr);
            dl.setAttribute("download", "backup_absensi.json");
            document.body.appendChild(dl); dl.click(); dl.remove();
        };

        window.importDatabase = function(e) {
            const file = e.target.files[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(evt) {
                try {
                    db = JSON.parse(evt.target.result);
                    saveToLocalStorage();
                    location.reload();
                } catch(err) { alert("File salah!"); }
            };
            reader.readAsText(file);
        };

        window.resetDatabase = function() {
            if (confirm("Reset semua data?")) {
                localStorage.removeItem("barcode_attendance_db_v5_1");
                location.reload();
            }
        };
    </script>
</body>
</html>

```
