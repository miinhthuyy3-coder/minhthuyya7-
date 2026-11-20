# minhthuyya7-
nghe nhạc thư giản sau những giờ học căng thẳng 
# Minhthuyya7
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Giai Điệu Nhẹ Nhàng — Chill & Relax Music</title>
    <!-- Nhúng Google Fonts thanh mảnh, hiện đại, hỗ trợ tiếng Việt đẹp -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600&family=Quicksand:wght@400;500;600&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-gradient: linear-gradient(135deg, #e0f2fe 0%, #f0fdf4 50%, #e6f4f1 100%);
            --card-bg: rgba(255, 255, 255, 0.78);
            --primary-blue: #38bdf8;
            --soft-blue: #7dd3fc;
            --deep-slate: #334155;
            --muted-text: #64748b;
            --accent-mint: #5eead4;
            --border-light: rgba(186, 230, 253, 0.8);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            font-weight: 300;
            background: var(--bg-gradient);
            color: var(--deep-slate);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px 20px;
            line-height: 1.6;
        }

        /* Header nhẹ nhàng */
        header {
            text-align: center;
            max-width: 650px;
            margin-bottom: 40px;
        }

        .badge {
            display: inline-block;
            background-color: #e0f2fe;
            color: #0284c7;
            padding: 6px 16px;
            border-radius: 999px;
            font-size: 0.85rem;
            font-weight: 500;
            letter-spacing: 0.5px;
            margin-bottom: 14px;
            border: 1px solid #bae6fd;
        }

        h1 {
            font-family: 'Quicksand', sans-serif;
            font-weight: 500;
            font-size: 2.5rem;
            color: #0f172a;
            margin-bottom: 12px;
            letter-spacing: -0.5px;
        }

        header p {
            color: var(--muted-text);
            font-size: 1.05rem;
            font-weight: 300;
        }

        /* Khung trình phát nhạc chính */
        .container {
            width: 100%;
            max-width: 820px;
            display: grid;
            gap: 24px;
        }

        .now-playing {
            background: var(--card-bg);
            backdrop-filter: blur(12px);
            border: 1px solid var(--border-light);
            border-radius: 24px;
            padding: 30px;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 28px;
            box-shadow: 0 10px 30px rgba(14, 165, 233, 0.08);
        }

        .album-art {
            width: 140px;
            height: 140px;
            border-radius: 20px;
            background: linear-gradient(135deg, #bae6fd, #a7f3d0);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: #0369a1;
            box-shadow: 0 8px 20px rgba(56, 189, 248, 0.2);
            flex-shrink: 0;
        }

        .track-info {
            flex: 1;
            min-width: 240px;
        }

        .track-info h2 {
            font-family: 'Quicksand', sans-serif;
            font-weight: 600;
            font-size: 1.5rem;
            color: #0f172a;
            margin-bottom: 4px;
        }

        .track-info .artist {
            color: #0284c7;
            font-size: 0.95rem;
            font-weight: 400;
            margin-bottom: 18px;
        }

        /* Thanh tiến trình mô phỏng */
        .progress-container {
            width: 100%;
            margin-bottom: 16px;
        }

        .progress-bar {
            width: 100%;
            height: 6px;
            background-color: #e0f2fe;
            border-radius: 10px;
            overflow: hidden;
            cursor: pointer;
        }

        .progress-fill {
            width: 38%;
            height: 100%;
            background: linear-gradient(90deg, #38bdf8, #34d399);
            border-radius: 10px;
            transition: width 0.3s ease;
        }

        .time-labels {
            display: flex;
            justify-content: space-between;
            font-size: 0.8rem;
            color: var(--muted-text);
            margin-top: 6px;
        }

        /* Nút điều khiển */
        .controls {
            display: flex;
            align-items: center;
            gap: 16px;
        }

        .btn {
            border: none;
            background: #f0f9ff;
            color: #0284c7;
            width: 42px;
            height: 42px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s ease;
        }

        .btn:hover {
            background: #e0f2fe;
            transform: translateY(-2px);
        }

        .btn-play {
            width: 52px;
            height: 52px;
            background: linear-gradient(135deg, #38bdf8, #0ea5e9);
            color: white;
            font-size: 1.2rem;
            box-shadow: 0 6px 16px rgba(14, 165, 233, 0.3);
        }

        .btn-play:hover {
            background: linear-gradient(135deg, #0ea5e9, #0284c7);
        }

        /* Danh sách phát (Playlist) */
        .playlist-card {
            background: var(--card-bg);
            backdrop-filter: blur(12px);
            border: 1px solid var(--border-light);
            border-radius: 24px;
            padding: 24px 28px;
            box-shadow: 0 10px 30px rgba(14, 165, 233, 0.05);
        }

        .playlist-card h3 {
            font-family: 'Quicksand', sans-serif;
            font-weight: 600;
            font-size: 1.2rem;
            margin-bottom: 16px;
            color: #0f172a;
        }

        .song-list {
            list-style: none;
        }

        .song-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px 16px;
            border-radius: 14px;
            transition: background 0.2s ease;
            cursor: pointer;
            border-bottom: 1px solid rgba(224, 242, 254, 0.6);
        }

        .song-item:last-child {
            border-bottom: none;
        }

        .song-item:hover {
            background-color: rgba(224, 242, 254, 0.55);
        }

        .song-item.active {
            background-color: #e0f2fe;
        }

        .song-left {
            display: flex;
            align-items: center;
            gap: 14px;
        }

        .song-num {
            color: #0284c7;
            font-weight: 500;
            width: 20px;
        }

        .song-title {
            font-weight: 500;
            color: #1e293b;
            font-size: 0.98rem;
        }

        .song-sub {
            font-size: 0.82rem;
            color: var(--muted-text);
        }

        .song-duration {
            font-size: 0.85rem;
            color: #0284c7;
            font-weight: 400;
        }

        footer {
            margin-top: 40px;
            font-size: 0.85rem;
            color: var(--muted-text);
            text-align: center;
        }

        @media (max-width: 600px) {
            h1 { font-size: 1.9rem; }
            .now-playing { justify-content: center; text-align: center; }
            .controls { justify-content: center; }
        }
    </style>
</head>
<body>

    <header>
        <span class="badge">☁️ Chill & Acoustic Space</span>
        <h1>Giai Điệu Thanh Bình</h1>
        <p>Thả lỏng tâm trí cùng những bản nhạc piano và tiếng mưa dịu nhẹ mỗi ngày.</p>
    </header>

    <main class="container">
        <!-- Trình phát nhạc hiện tại -->
        <section class="now-playing">
            <div class="album-art">🎵</div>
            <div class="track-info">
                <h2 id="current-title">Mưa Nhẹ Bên Cửa Sổ</h2>
                <p class="artist" id="current-artist">An Yên Piano • Album: Chiều Xanh</p>
                
                <div class="progress-container">
                    <div class="progress-bar" onclick="seek(event)">
                        <div class="progress-fill" id="progress-fill"></div>
                    </div>
                    <div class="time-labels">
                        <span>01:24</span>
                        <span id="current-duration">03:45</span>
                    </div>
                </div>

                <div class="controls">
                    <button class="btn" title="Bài trước" onclick="prevSong()">⏮</button>
                    <button class="btn btn-play" id="play-btn" title="Phát / Tạm dừng" onclick="togglePlay()">▶</button>
                    <button class="btn" title="Bài tiếp theo" onclick="nextSong()">⏭</button>
                </div>
            </div>
        </section>

        <!-- Danh sách nhạc -->
        <section class="playlist-card">
            <h3>Danh sách phát nhẹ nhàng</h3>
            <ul class="song-list" id="song-list">
                <li class="song-item active" onclick="selectSong(0)">
                    <div class="song-left">
                        <span class="song-num">01</span>
                        <div>
                            <div class="song-title">Mưa Nhẹ Bên Cửa Sổ</div>
                            <div class="song-sub">An Yên Piano • Acoustic</div>
                        </div>
                    </div>
                    <span class="song-duration">03:45</span>
                </li>
                <li class="song-item" onclick="selectSong(1)">
                    <div class="song-left">
                        <span class="song-num">02</span>
                        <div>
                            <div class="song-title">Gió Biển Buổi Sớm</div>
                            <div class="song-sub">Mây Trắng • Lo-fi Chill</div>
                        </div>
                    </div>
                    <span class="song-duration">04:12</span>
                </li>
                <li class="song-item" onclick="selectSong(2)">
                    <div class="song-left">
                        <span class="song-num">03</span>
                        <div>
                            <div class="song-title">Dưới Tán Lá Xanh</div>
                            <div class="song-sub">Hạ Miên • Guitar Nhẹ</div>
                        </div>
                    </div>
                    <span class="song-duration">02:58</span>
                </li>
                <li class="song-item" onclick="selectSong(3)">
                    <div class="song-left">
                        <span class="song-num">04</span>
                        <div>
                            <div class="song-title">Ánh Trăng Trên Mặt Hồ</div>
                            <div class="song-sub">Nhật Minh • Nhạc Không Lời</div>
                        </div>
                    </div>
                    <span class="song-duration">05:04</span>
                </li>
            </ul>
        </section>
    </main>

    <footer>
        Thiết kế nhẹ nhàng với tông xanh pastel • Dành cho những phút giây thư giãn
    </footer>

    <script>
        const songs = [
            { title: "Mưa Nhẹ Bên Cửa Sổ", artist: "An Yên Piano • Album: Chiều Xanh", duration: "03:45" },
            { title: "Gió Biển Buổi Sớm", artist: "Mây Trắng • Album: Biển Xanh", duration: "04:12" },
            { title: "Dưới Tán Lá Xanh", artist: "Hạ Miên • Album: Khu Vườn Nhỏ", duration: "02:58" },
            { title: "Ánh Trăng Trên Mặt Hồ", artist: "Nhật Minh • Album: Đêm Tĩnh Lặng", duration: "05:04" }
        ];

        let currentIndex = 0;
        let isPlaying = false;

        function selectSong(index) {
            currentIndex = index;
            document.getElementById('current-title').textContent = songs[index].title;
            document.getElementById('current-artist').textContent = songs[index].artist;
            document.getElementById('current-duration').textContent = songs[index].duration;

            const items = document.querySelectorAll('.song-item');
            items.forEach((item, idx) => {
                item.classList.toggle('active', idx === index);
            });

            isPlaying = true;
            document.getElementById('play-btn').textContent = '⏸';
        }

        function togglePlay() {
            isPlaying = !isPlaying;
            document.getElementById('play-btn').textContent = isPlaying ? '⏸' : '▶';
        }

        function nextSong() {
            selectSong((currentIndex + 1) % songs.length);
        }

        function prevSong() {
            selectSong((currentIndex - 1 + songs.length) % songs.length);
        }

        function seek(event) {
            const bar = event.currentTarget;
            const percent = (event.offsetX / bar.offsetWidth) * 100;
            document.getElementById('progress-fill').style.width = percent + '%';
        }
    </script>
</body>
</html>
