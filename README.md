<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VisionX</title>

<style>
:root {
    --bg: #080b12;
    --panel: #111722;
    --panel2: #171f2d;
    --border: #263244;
    --text: #e9eef6;
    --muted: #8b98ab;
    --green: #00e676;
    --red: #ff4d61;
    --orange: #ffb020;
    --blue: #3b82f6;
}

* {
    box-sizing: border-box;
}

body {
    margin: 0;
    background: var(--bg);
    color: var(--text);
    font-family: Inter, Arial, sans-serif;
}

button {
    cursor: pointer;
    border: none;
    font-family: inherit;
}

.app {
    display: flex;
    min-height: 100vh;
}

/* SIDEBAR */

.sidebar {
    width: 240px;
    background: #0d121b;
    border-right: 1px solid var(--border);
    padding: 25px 18px;
}

.logo {
    font-size: 25px;
    font-weight: 800;
    letter-spacing: 2px;
}

.logo span {
    color: var(--green);
}

.subtitle {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 3px;
    margin-top: 5px;
}

.nav {
    margin-top: 40px;
}

.nav-item {
    padding: 13px;
    margin-bottom: 8px;
    border-radius: 10px;
    color: var(--muted);
    cursor: pointer;
}

.nav-item.active {
    background: rgba(0,230,118,0.1);
    color: var(--green);
}

/* MAIN */

.main {
    flex: 1;
    padding: 35px;
    overflow: hidden;
}

.topbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 30px;
}

.topbar h1 {
    margin: 0;
    font-size: 27px;
}

.topbar p {
    color: var(--muted);
    margin-top: 8px;
}

.import-btn {
    background: var(--green);
    color: #06130c;
    padding: 12px 18px;
    border-radius: 10px;
    font-weight: 700;
}

/* STATISTICS */

.stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 18px;
    margin-bottom: 30px;
}

.stat-card {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 22px;
    border-radius: 15px;
}

.stat-label {
    color: var(--muted);
    font-size: 13px;
}

.stat-value {
    font-size: 32px;
    font-weight: 800;
    margin-top: 12px;
}

.stat-total {
    color: white;
}

.stat-online {
    color: var(--green);
}

.stat-offline {
    color: var(--red);
}

/* PLAYLIST */

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 18px;
}

.section-header h2 {
    font-size: 18px;
}

.search {
    background: var(--panel);
    border: 1px solid var(--border);
    color: white;
    padding: 12px;
    border-radius: 10px;
    outline: none;
    width: 250px;
}

.playlist-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 18px;
}

.playlist-card {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 20px;
    border-radius: 15px;
    transition: .2s;
}

.playlist-card:hover {
    border-color: #3b4659;
    transform: translateY(-2px);
}

.playlist-title {
    font-size: 17px;
    font-weight: 700;
}

.playlist-url {
    font-size: 11px;
    color: var(--muted);
    margin-top: 10px;
    overflow-wrap: anywhere;
}

.playlist-count {
    margin-top: 18px;
    color: var(--muted);
    font-size: 13px;
}

.status-row {
    display: flex;
    gap: 15px;
    margin-top: 15px;
    font-size: 13px;
}

.online {
    color: var(--green);
}

.offline {
    color: var(--red);
}

.unknown {
    color: var(--orange);
}

.card-actions {
    display: flex;
    gap: 8px;
    margin-top: 20px;
    flex-wrap: wrap;
}

.action-btn {
    padding: 9px 12px;
    border-radius: 8px;
    background: var(--panel2);
    color: var(--text);
    font-size: 12px;
}

.action-btn:hover {
    background: #243246;
}

.delete-btn {
    color: var(--red);
}

/* EMPTY */

.empty {
    padding: 50px 20px;
    text-align: center;
    color: var(--muted);
    border: 1px dashed var(--border);
    border-radius: 15px;
}

/* MODAL */

.modal {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,.75);
    justify-content: center;
    align-items: center;
    z-index: 100;
    padding: 20px;
}

.modal.show {
    display: flex;
}

.modal-content {
    width: 100%;
    max-width: 500px;
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 18px;
    padding: 25px;
}

.modal-content h2 {
    margin-top: 0;
}

.form-group {
    margin-top: 20px;
}

.form-group label {
    display: block;
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 8px;
}

.form-group input {
    width: 100%;
    padding: 13px;
    border-radius: 10px;
    background: #080d15;
    color: white;
    border: 1px solid var(--border);
    outline: none;
}

.modal-actions {
    display: flex;
    justify-content: flex-end;
    gap: 10px;
    margin-top: 25px;
}

.cancel-btn {
    background: var(--panel2);
    color: white;
    padding: 12px 16px;
    border-radius: 9px;
}

.save-btn {
    background: var(--green);
    color: #04130a;
    padding: 12px 16px;
    border-radius: 9px;
    font-weight: 700;
}

.toast {
    position: fixed;
    bottom: 25px;
    right: 25px;
    background: var(--panel2);
    border: 1px solid var(--border);
    padding: 15px 20px;
    border-radius: 10px;
    display: none;
    z-index: 200;
}

/* CHANNEL LIST */

.channel-container {
    display: none;
    margin-top: 25px;
}

.channel-container.show {
    display: block;
}

.channel-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 15px;
}

.channel-list {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    max-height: 600px;
    overflow-y: auto;
}

.channel-item {
    padding: 13px 16px;
    border-bottom: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    gap: 10px;
}

.channel-item:last-child {
    border-bottom: none;
}

.channel-name {
    font-size: 13px;
}

.channel-status {
    font-size: 12px;
}

/* RESPONSIVE */

@media (max-width: 900px) {
    .sidebar {
        display: none;
    }

    .main {
        padding: 20px;
    }

    .stats {
        grid-template-columns: 1fr;
    }

    .topbar {
        flex-direction: column;
        align-items: flex-start;
        gap: 15px;
    }

    .section-header {
        flex-direction: column;
        align-items: flex-start;
        gap: 12px;
    }

    .search {
        width: 100%;
    }
}
</style>
</head>

<body>

<div class="app">

    <aside class="sidebar">
        <div class="logo">VISION<span>X</span></div>
        <div class="subtitle">STREAM MANAGEMENT</div>

        <div class="nav">
            <div class="nav-item active">📊 Dashboard</div>
            <div class="nav-item">📁 Playlists</div>
        </div>
    </aside>

    <main class="main">

        <div class="topbar">
            <div>
                <h1>Dashboard</h1>
                <p>Deine Playlist-Übersicht</p>
            </div>

            <button class="import-btn" onclick="openModal()">
                ＋ Import Playlist
            </button>
        </div>

        <div class="stats">

            <div class="stat-card">
                <div class="stat-label">TOTAL STREAMS</div>
                <div class="stat-value stat-total" id="totalStreams">0</div>
            </div>

            <div class="stat-card">
                <div class="stat-label">ONLINE</div>
                <div class="stat-value stat-online" id="onlineStreams">0</div>
            </div>

            <div class="stat-card">
                <div class="stat-label">OFFLINE</div>
                <div class="stat-value stat-offline" id="offlineStreams">0</div>
            </div>

        </div>

        <div class="section-header">
            <h2>Meine Playlists</h2>
            <input
                class="search"
                id="searchInput"
                placeholder="🔍 Playlist suchen..."
                oninput="renderPlaylists()"
            >
        </div>

        <div id="playlistGrid" class="playlist-grid"></div>

        <div id="channelContainer" class="channel-container">
            <div class="channel-header">
                <h2 id="channelTitle">Channels</h2>
                <button class="action-btn" onclick="closeChannels()">← Zurück</button>
            </div>

            <div class="channel-list" id="channelList"></div>
        </div>

    </main>

</div>

<!-- IMPORT MODAL -->

<div class="modal" id="importModal">
    <div class="modal-content">

        <h2>Playlist importieren</h2>

        <div class="form-group">
            <label>Playlist Name</label>
            <input id="playlistName" placeholder="z.B. Türkei TV">
        </div>

        <div class="form-group">
            <label>M3U Playlist URL</label>
            <input id="playlistUrl" placeholder="https://example.com/playlist.m3u">
        </div>

        <div class="modal-actions">
            <button class="cancel-btn" onclick="closeModal()">Abbrechen</button>
            <button class="save-btn" onclick="importPlaylist()">Importieren</button>
        </div>

    </div>
</div>

<div class="toast" id="toast"></div>

<script>

/* STORAGE */

let playlists = JSON.parse(localStorage.getItem("visionx_playlists") || "[]");

function saveData() {
    localStorage.setItem("visionx_playlists", JSON.stringify(playlists));
}

/* UI */

function openModal() {
    document.getElementById("importModal").classList.add("show");
}

function closeModal() {
    document.getElementById("importModal").classList.remove("show");
}

function showToast(message) {
    const toast = document.getElementById("toast");
    toast.textContent = message;
    toast.style.display = "block";

    setTimeout(() => {
        toast.style.display = "none";
    }, 3000);
}

/* PLAYLIST IMPORT */

async function importPlaylist() {

    const name = document.getElementById("playlistName").value.trim();
    const url = document.getElementById("playlistUrl").value.trim();

    if (!name || !url) {
        showToast("Bitte Name und URL eingeben.");
        return;
    }

    showToast("Playlist wird geladen...");

    try {

        const response = await fetch(url);

        if (!response.ok) {
            throw new Error("Playlist konnte nicht geladen werden.");
        }

        const text = await response.text();

        const channels = parseM3U(text);

        const playlist = {
            id: Date.now(),
            name: name,
            url: url,
            channels: channels,
            importedAt: new Date().toISOString()
        };

        playlists.push(playlist);

        saveData();

        closeModal();

        document.getElementById("playlistName").value = "";
        document.getElementById("playlistUrl").value = "";

        renderPlaylists();

        showToast(channels.length + " Streams importiert.");

    } catch (error) {

        showToast("Import fehlgeschlagen. Möglicherweise CORS-Sperre.");

    }

}

/* M3U PARSER */

function parseM3U(text) {

    const lines = text.split(/\r?\n/);
    const channels = [];

    let currentName = "Unbekannter Kanal";

    for (let line of lines) {

        line = line.trim();

        if (line.startsWith("#EXTINF")) {

            const comma = line.lastIndexOf(",");

            if (comma !== -1) {
                currentName = line.substring(comma + 1).trim();
            }

        } else if (
            line &&
            !line.startsWith("#")
        ) {

            channels.push({
                name: currentName,
                url: line,
                status: "unknown"
            });

            currentName = "Unbekannter Kanal";

        }

    }

    return channels;
}

/* RENDER */

function renderPlaylists() {

    const grid = document.getElementById("playlistGrid");
    const search = document.getElementById("searchInput").value.toLowerCase();

    grid.innerHTML = "";

    let total = 0;
    let online = 0;
    let offline = 0;

    playlists.forEach(playlist => {

        total += playlist.channels.length;

        playlist.channels.forEach(channel => {

            if (channel.status === "online") online++;
            if (channel.status === "offline") offline++;

        });

        if (!playlist.name.toLowerCase().includes(search)) {
            return;
        }

        const card = document.createElement("div");
        card.className = "playlist-card";

        const onlineCount = playlist.channels.filter(c => c.status === "online").length;
        const offlineCount = playlist.channels.filter(c => c.status === "offline").length;
        const unknownCount = playlist.channels.filter(c => c.status === "unknown").length;

        card.innerHTML = `
            <div class="playlist-title">📁 ${escapeHTML(playlist.name)}</div>

            <div class="playlist-url">
                ${escapeHTML(playlist.url)}
            </div>

            <div class="playlist-count">
                ${playlist.channels.length} Channels
            </div>

            <div class="status-row">
                <span class="online">🟢 ${onlineCount}</span>
                <span class="offline">🔴 ${offlineCount}</span>
                <span class="unknown">🟠 ${unknownCount}</span>
            </div>

            <div class="card-actions">

                <button class="action-btn"
                    onclick="openChannels(${playlist.id})">
                    Öffnen
                </button>

                <button class="action-btn"
                    onclick="checkPlaylist(${playlist.id})">
                    Prüfen
                </button>

                <button class="action-btn delete-btn"
                    onclick="deletePlaylist(${playlist.id})">
                    Löschen
                </button>

            </div>
        `;

        grid.appendChild(card);

    });

    document.getElementById("totalStreams").textContent = total;
    document.getElementById("onlineStreams").textContent = online;
    document.getElementById("offlineStreams").textContent = offline;

    if (playlists.length === 0) {

        grid.innerHTML = `
            <div class="empty">
                <h3>Noch keine Playlists</h3>
                <p>Importiere deine erste M3U Playlist.</p>
            </div>
        `;

    }

}

/* CHANNELS */

function openChannels(id) {

    const playlist = playlists.find(p => p.id === id);

    if (!playlist) return;

    document.getElementById("channelTitle").textContent =
        playlist.name + " – " + playlist.channels.length + " Channels";

    const list = document.getElementById("channelList");

    list.innerHTML = "";

    playlist.channels.forEach(channel => {

        const item = document.createElement("div");
        item.className = "channel-item";

        let statusText = "🟠 Unbekannt";

        if (channel.status === "online") statusText = "🟢 Online";
        if (channel.status === "offline") statusText = "🔴 Offline";

        item.innerHTML = `
            <div class="channel-name">${escapeHTML(channel.name)}</div>
            <div class="channel-status">${statusText}</div>
        `;

        list.appendChild(item);

    });

    document.getElementById("channelContainer").classList.add("show");
}

/* CLOSE CHANNELS */

function closeChannels() {
    document.getElementById("channelContainer").classList.remove("show");
}

/* DELETE */

function deletePlaylist(id) {

    if (!confirm("Playlist wirklich löschen?")) return;

    playlists = playlists.filter(p => p.id !== id);

    saveData();
    renderPlaylists();

    showToast("Playlist gelöscht.");

}

/* CHECK */

async function checkPlaylist(id) {

    const playlist = playlists.find(p => p.id === id);

    if (!playlist) return;

    showToast("Prüfung gestartet...");

    for (const channel of playlist.channels) {

        try {

            const response = await fetch(channel.url, {
                method: "GET",
                mode: "no-cors"
            });

            channel.status = "online";

        } catch (error) {

            channel.status = "offline";

        }

    }

    saveData();
    renderPlaylists();

    showToast("Prüfung abgeschlossen.");

}

/* SECURITY */

function escapeHTML(text) {

    return String(text)
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/"/g, "&quot;")
        .replace(/'/g, "&#039;");

}

/* INITIALIZE */

renderPlaylists();

</script>

</body>
</html>
