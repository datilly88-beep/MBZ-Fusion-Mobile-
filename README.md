# MBZ-Fusion-Mobile-l

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>MBZ Omega – Fusion Mobile</title>

<style>
    :root {
        --bg: #050509;
        --panel: #101018;
        --panel-soft: #161624;
        --border: #252535;
        --accent-up: #39ffb5;
        --accent-down: #ff5f7a;
        --accent-neutral: #6cf0ff;
        --accent-gold: #ffd37a;
        --text-main: #f5f5ff;
        --text-soft: #b2b2c8;
        --danger: #ff4b81;
        --good: #32ff92;
        --omega-purple: #b173ff;
    }

    * {
        box-sizing: border-box;
    }

    body {
        font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text",
            "Segoe UI", Roboto, sans-serif;
        background: radial-gradient(circle at top, #101020 0, #050509 40%, #000 100%);
        color: var(--text-main);
        margin: 0;
        padding: 0;
    }

    header {
        padding: 14px 16px 10px;
        border-bottom: 1px solid #12121e;
        position: sticky;
        top: 0;
        z-index: 10;
        background: rgba(5, 5, 9, 0.95);
        backdrop-filter: blur(12px);
    }

    .header-title {
        font-size: 18px;
        font-weight: 600;
        display: flex;
        align-items: baseline;
        justify-content: space-between;
    }

    .header-title span:nth-child(1) {
        letter-spacing: 0.06em;
        text-transform: uppercase;
        color: var(--accent-neutral);
        font-size: 11px;
    }

    .header-title span:nth-child(2) {
        font-size: 16px;
        color: #ffffff;
    }

    .phase-pill {
        display: inline-flex;
        align-items: center;
        gap: 6px;
        padding: 4px 10px;
        border-radius: 999px;
        background: linear-gradient(90deg, #2f2f4a, #181822);
        border: 1px solid #454578;
        font-size: 11px;
        margin-top: 6px;
    }

    .phase-dot {
        width: 6px;
        height: 6px;
        border-radius: 999px;
        background: var(--good);
        box-shadow: 0 0 10px rgba(50, 255, 146, 0.9);
    }

    .phase-label {
        text-transform: uppercase;
        letter-spacing: 0.08em;
        color: #e7e7ff;
    }

    .phase-mode {
        opacity: 0.75;
    }

    main {
        padding: 12px 12px 80px;
        max-width: 520px;
        margin: 0 auto;
    }

    .section-title {
        font-size: 14px;
        font-weight: 600;
        color: var(--text-soft);
        text-transform: uppercase;
        letter-spacing: 0.12em;
        margin: 10px 2px 6px;
    }

    .deck {
        display: flex;
        flex-direction: column;
        gap: 10px;
    }

    .card {
        background: radial-gradient(circle at top left, #26264a22, #101018 55%);
        border-radius: 12px;
        padding: 12px 12px 10px;
        border: 1px solid rgba(63, 63, 100, 0.5);
        box-shadow: 0 0 0 1px #141425, 0 18px 40px rgba(0, 0, 0, 0.6);
        position: relative;
        overflow: hidden;
    }

    .card-header {
        display: flex;
        justify-content: space-between;
        align-items: baseline;
        margin-bottom: 8px;
    }

    .card-title {
        font-size: 14px;
        font-weight: 600;
        display: flex;
        align-items: center;
        gap: 6px;
    }

    .card-title span.icon {
        font-size: 15px;
    }

    .card-sub {
        font-size: 11px;
        text-transform: uppercase;
        letter-spacing: 0.12em;
        color: var(--text-soft);
    }

    .pill {
        display: inline-flex;
        align-items: center;
        padding: 3px 8px;
        border-radius: 999px;
        font-size: 10px;
        letter-spacing: 0.08em;
        text-transform: uppercase;
        border: 1px solid rgba(255, 255, 255, 0.12);
        background: rgba(255, 255, 255, 0.02);
        color: var(--text-soft);
        gap: 4px;
    }

    .pill--up {
        border-color: rgba(57, 255, 181, 0.6);
        color: var(--accent-up);
        box-shadow: 0 0 10px rgba(57, 255, 181, 0.3);
    }
    .pill--down {
        border-color: rgba(255, 95, 122, 0.7);
        color: var(--accent-down);
        box-shadow: 0 0 10px rgba(255, 95, 122, 0.35);
    }

    .pill-dot {
        width: 6px;
        height: 6px;
        border-radius: 999px;
        background: currentColor;
    }

    .mpd-grid {
        display: grid;
        grid-template-columns: 1.3fr 1fr;
        gap: 10px;
        align-items: stretch;
        margin-top: 6px;
    }

    .field-label {
        font-size: 11px;
        text-transform: uppercase;
        letter-spacing: 0.12em;
        color: var(--text-soft);
        margin-bottom: 2px;
    }

    .field-value {
        font-size: 14px;
        font-weight: 500;
        color: var(--text-main);
    }

    .field-note {
        font-size: 11px;
        color: var(--text-soft);
        margin-top: 2px;
    }

    .mpd-direction {
        font-size: 16px;
        font-weight: 600;
        text-shadow: 0 0 12px rgba(0, 255, 188, 0.8);
    }

    .mpd-direction.down {
        color: var(--accent-down);
        text-shadow: 0 0 12px rgba(255, 95, 122, 0.85);
    }

    .mpd-direction.flat {
        color: var(--accent-neutral);
        text-shadow: 0 0 12px rgba(108, 240, 255, 0.7);
    }

    .mini-kpi-row {
        display: flex;
        gap: 8px;
        margin-top: 6px;
    }

    .mini-kpi {
        flex: 1;
        background: rgba(9, 9, 15, 0.9);
        border-radius: 8px;
        padding: 6px 8px;
        border: 1px solid rgba(62, 62, 100, 0.6);
        font-size: 11px;
    }

    .mini-kpi strong {
        display: block;
        font-size: 12px;
        margin-bottom: 2px;
        color: var(--accent-gold);
    }

    .channel-strip {
        margin-top: 6px;
        border-radius: 999px;
        padding: 6px 8px;
        background: linear-gradient(90deg,
            rgba(57, 255, 181, 0.2),
            rgba(108, 240, 255, 0.1),
            rgba(177, 115, 255, 0.28),
            rgba(255, 95, 122, 0.2)
        );
        border: 1px solid rgba(120, 120, 190, 0.7);
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 10px;
        font-size: 11px;
    }

    .channel-label {
        text-transform: uppercase;
        letter-spacing: 0.12em;
        color: #e7e7ff;
    }

    .channel-modes {
        display: flex;
        gap: 6px;
        flex-wrap: wrap;
        justify-content: flex-end;
    }

    .chip {
        padding: 3px 8px;
        border-radius: 999px;
        background: rgba(6, 6, 12, 0.85);
        border: 1px solid rgba(255, 255, 255, 0.06);
        font-size: 10px;
        color: var(--text-soft);
    }

    .chip--hot {
        border-color: rgba(255, 176, 103, 0.9);
        color: var(--accent-gold);
        box-shadow: 0 0 8px rgba(255, 211, 122, 0.6);
    }

    .chip--void {
        border-color: rgba(108, 240, 255, 0.5);
        color: var(--accent-neutral);
        opacity: 0.85;
    }

    .mtf-row {
        display: grid;
        grid-template-columns: repeat(4, minmax(0, 1fr));
        gap: 6px;
        margin-top: 6px;
    }

    .mtf-cell {
        background: var(--panel-soft);
        border-radius: 10px;
        padding: 6px 6px 5px;
        border: 1px solid var(--border);
        font-size: 10px;
    }

    .mtf-tf {
        text-transform: uppercase;
        letter-spacing: 0.12em;
        color: var(--text-soft);
        margin-bottom: 4px;
    }

    .mtf-bias {
        font-size: 11px;
        font-weight: 500;
    }

    .mtf-bias.up {
        color: var(--accent-up);
    }

    .mtf-bias.down {
        color: var(--accent-down);
    }

    .mtf-bias.neutral {
        color: var(--accent-neutral);
    }

    .mtf-tag {
        float: right;
        font-size: 9px;
        text-transform: uppercase;
        opacity: 0.7;
    }

    .history-wrap {
        margin-top: 8px;
        background: radial-gradient(circle at top, #24244833, #090912);
        border-radius: 10px;
        border: 1px solid #2e2e52;
        padding: 8px 8px 6px;
    }

    .history-header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        font-size: 11px;
        color: var(--text-soft);
        margin-bottom: 4px;
    }

    .history-header strong {
        text-transform: uppercase;
        letter-spacing: 0.12em;
        font-size: 10px;
        color: var(--accent-neutral);
    }

    .history-meta {
        font-size: 10px;
        opacity: 0.75;
    }

    .history-svg {
        width: 100%;
        height: 60px;
    }

    .history-path {
        fill: none;
        stroke: var(--accent-up);
        stroke-width: 2;
        stroke-linecap: round;
        stroke-linejoin: round;
        filter: drop-shadow(0 0 6px rgba(57, 255, 181, 0.7));
    }

    .history-baseline {
        stroke: rgba(160, 160, 210, 0.35);
        stroke-width: 1;
        stroke-dasharray: 4 3;
    }

    .history-dot {
        fill: var(--accent-up);
        filter: drop-shadow(0 0 5px rgba(57, 255, 181, 0.7));
    }

    .history-dot.down {
        fill: var(--accent-down);
        filter: drop-shadow(0 0 5px rgba(255, 95, 122, 0.7));
    }

    .history-empty {
        font-size: 11px;
        color: var(--text-soft);
        text-align: center;
        padding: 12px 0 4px;
    }

    .footer-strip {
        position: fixed;
        bottom: 0;
        left: 0;
        right: 0;
        padding: 6px 14px 10px;
        background: linear-gradient(180deg, rgba(5, 5, 10, 0.2), #050509 55%);
        border-top: 1px solid #181826;
        display: flex;
        justify-content: space-between;
        align-items: center;
        max-width: 520px;
        margin: 0 auto;
        inset-inline: 0;
    }

    .footer-badge {
        font-size: 10px;
        color: var(--text-soft);
    }

    .footer-badge span {
        text-transform: uppercase;
        letter-spacing: 0.13em;
        color: var(--omega-purple);
    }

    .btn {
        border-radius: 999px;
        border: 1px solid rgba(108, 240, 255, 0.9);
        background: radial-gradient(circle at top, #3636a8, #151526);
        color: #e6ffff;
        padding: 6px 10px;
        font-size: 11px;
        display: inline-flex;
        align-items: center;
        gap: 6px;
        text-transform: uppercase;
        letter-spacing: 0.12em;
    }

    .btn span.icon {
        font-size: 14px;
    }

    @media (max-width: 360px) {
        .mtf-row {
            grid-template-columns: repeat(2, minmax(0, 1fr));
        }
    }
</style>
</head>

<body>
<header>
    <div class="header-title">
        <div>
            <span>MBZ Ω</span><br />
            <span>Fusion Mobile Console</span>
        </div>
        <div style="text-align:right;font-size:11px;color:var(--text-soft);">
            <div>SPY · ES · QQQ Cluster</div>
            <div id="lastUpdateLabel">Waiting…</div>
        </div>
    </div>

    <div class="phase-pill">
        <div class="phase-dot" id="phaseDot"></div>
        <div class="phase-label" id="phaseLabel">Coherence</div>
        <div class="phase-mode" id="phaseMode">Bull · Trend</div>
    </div>
</header>

<main>
    <!-- LIVE MPD / FLOW -->
    <div class="section-title">Live Engine</div>
    <div class="deck">
        <section class="card">
            <div class="card-header">
                <div class="card-title">
                    <span class="icon">⚡</span>
                    <span>Micro Pressure Detector</span>
                </div>
                <div id="mpdPill" class="pill pill--up">
                    <span class="pill-dot"></span>Flow Up
                </div>
            </div>
            <div class="card-sub">MPD · Sequence · Bias</div>

            <div class="mpd-grid">
                <div>
                    <div class="field-label">Direction</div>
                    <div id="mpdDirection" class="field-value mpd-direction">
                        Loading…
                    </div>

                    <div class="field-label" style="margin-top:8px;">Sequence</div>
                    <div id="mpdSequence" class="field-value">
                        —
                    </div>

                    <div id="mpdSequenceNote" class="field-note">
                        Awaiting first packet.
                    </div>
                </div>

                <div>
                    <div class="field-label">Bias</div>
                    <div id="mpdBias" class="field-value">
                        —
                    </div>
                    <div id="mpdBiasNote" class="field-note">
                        Normal regime.
                    </div>

                    <div class="mini-kpi-row">
                        <div class="mini-kpi">
                            <strong>Pressure</strong>
                            <span id="mpdPressureScore">—</span>
                        </div>
                        <div class="mini-kpi">
                            <strong>Risk Gate</strong>
                            <span id="riskGateLabel">Idle</span>
                        </div>
                    </div>
                </div>
            </div>

            <div class="channel-strip">
                <div class="channel-label">Neon Channels</div>
                <div class="channel-modes">
                    <div id="flowModeBadge" class="chip chip--hot">Ultra Instinct</div>
                    <div id="voidBadge" class="chip chip--void">Void Shield: On</div>
                </div>
            </div>
        </section>

        <!-- MTF STACK -->
        <section class="card">
            <div class="card-header">
                <div class="card-title">
                    <span class="icon">📡</span>
                    <span>MTF Bias Stack</span>
                </div>
                <div class="pill">
                    Stack · 4H → 15M
                </div>
            </div>
            <div class="card-sub">DBZ Channels · ROI Cones Sentiment</div>

            <div class="mtf-row">
                <div class="mtf-cell">
                    <div class="mtf-tf">4h<span class="mtf-tag" id="tag4h">Core</span></div>
                    <div id="bias4h" class="mtf-bias neutral">Neutral</div>
                </div>
                <div class="mtf-cell">
                    <div class="mtf-tf">1h<span class="mtf-tag" id="tag1h">Flow</span></div>
                    <div id="bias1h" class="mtf-bias neutral">Neutral</div>
                </div>
                <div class="mtf-cell">
                    <div class="mtf-tf">30m<span class="mtf-tag" id="tag30m">Trigger</span></div>
                    <div id="bias30m" class="mtf-bias neutral">Neutral</div>
                </div>
                <div class="mtf-cell">
                    <div class="mtf-tf">15m<span class="mtf-tag" id="tag15m">Entry</span></div>
                    <div id="bias15m" class="mtf-bias neutral">Neutral</div>
                </div>
            </div>

            <div class="mini-kpi-row">
                <div class="mini-kpi">
                    <strong>Stack Score</strong>
                    <span id="stackScoreLabel">—</span>
                </div>
                <div class="mini-kpi">
                    <strong>Conflict</strong>
                    <span id="conflictLabel">—</span>
                </div>
            </div>
        </section>

        <!-- HISTORY / TREND ARC -->
        <section class="card">
            <div class="card-header">
                <div class="card-title">
                    <span class="icon">🌀</span>
                    <span>Trend Arc · Last 20 Packets</span>
                </div>
                <div class="pill">
                    History · MPD Strength
                </div>
            </div>

            <div class="history-wrap">
                <div class="history-header">
                    <strong>Arc</strong>
                    <div class="history-meta" id="historyMeta">
                        Waiting for packets…
                    </div>
                </div>

                <svg id="historySvg" class="history-svg">
                    <line x1="0" y1="30" x2="100%" y2="30" class="history-baseline"></line>
                    <path id="historyPath" class="history-path" d=""></path>
                    <!-- Dots will be injected dynamically -->
                </svg>

                <div id="historyEmpty" class="history-empty">
                    No history yet. Once Pine starts sending webhooks, your MPD curve will render here.
                </div>
            </div>
        </section>
    </div>
</main>

<footer class="footer-strip">
    <div class="footer-badge">
        Ω Phase:<span id="footerPhaseLabel"> Coherence · Bull</span>
    </div>
    <button class="btn" type="button" id="refreshBtn">
        <span class="icon">⟳</span> Refresh
    </button>
</footer>

<script>
    // ========= CONFIG =========
    // Set this to your backend URL (where server.js will run)
    const BACKEND_URL = "https://YOUR-BACKEND-URL"; // ← replace later

    // Polling interval (ms)
    const POLL_INTERVAL = 5000;

    // In-memory history (last N packets)
    const MAX_HISTORY = 20;
    const history = [];

    // Demo flag (if backend not reachable)
    let demoMode = false;
    let demoTick = 0;

    // ========= UTILITIES =========
    function formatTime(ts) {
        if (!ts) return "—";
        const d = new Date(ts);
        return d.toLocaleTimeString([], { hour: "2-digit", minute: "2-digit" });
    }

    function classifyDirection(dir) {
        if (!dir) return "flat";
        const s = String(dir).toLowerCase();
        if (s.includes("up") || s.includes("bull")) return "up";
        if (s.includes("down") || s.includes("bear")) return "down";
        return "flat";
    }

    function biasClass(bias) {
        if (!bias) return "neutral";
        const s = String(bias).toLowerCase();
        if (s.includes("bull")) return "up";
        if (s.includes("bear")) return "down";
        return "neutral";
    }

    function riskGateFromScore(score) {
        if (score == null || isNaN(score)) return "Idle";
        if (score > 0.8) return "Open Throttle";
        if (score > 0.6) return "Active";
        if (score > 0.4) return "Probe Only";
        return "Flat / Defense";
    }

    function stackConflictLabel(stackScore) {
        if (stackScore == null || isNaN(stackScore)) return "Unknown";
        if (stackScore > 0.8) return "Aligned";
        if (stackScore > 0.6) return "Mild Conflict";
        if (stackScore > 0.4) return "Mixed";
        return "Heavy Conflict";
    }

    function phaseFromPayload(p) {
        // Expect something like p.phaseTag, p.phaseMode
        const phaseTag = p.phaseTag || "Coherence";
        const phaseMode = p.phaseMode || "Bull";
        return { phaseTag, phaseMode };
    }

    // ========= UI UPDATE =========
    function applyPhaseUI(phaseTag, phaseMode) {
        const label = document.getElementById("phaseLabel");
        const mode = document.getElementById("phaseMode");
        const dot = document.getElementById("phaseDot");
        const footer = document.getElementById("footerPhaseLabel");

        label.textContent = phaseTag;
        mode.textContent = phaseMode;
        footer.textContent = " " + phaseTag + " · " + phaseMode;

        const tag = String(phaseTag).toLowerCase();

        if (tag.includes("void")) {
            dot.style.background = "#6cf0ff";
            dot.style.boxShadow = "0 0 10px rgba(108,240,255,0.9)";
        } else if (tag.includes("bear")) {
            dot.style.background = "#ff5f7a";
            dot.style.boxShadow = "0 0 10px rgba(255,95,122,0.9)";
        } else {
            dot.style.background = "#32ff92";
            dot.style.boxShadow = "0 0 10px rgba(50,255,146,0.9)";
        }
    }

    function updateMTFBias(id, value) {
        const el = document.getElementById(id);
        const cls = biasClass(value);
        el.className = "mtf-bias " + cls;
        el.textContent = value || "Neutral";
    }

    function updateUIFromState(state) {
        // --- MPD core ---
        const dirClass = classifyDirection(state.mpdDirection);
        const directionEl = document.getElementById("mpdDirection");
        directionEl.textContent = state.mpdDirection || "—";
        directionEl.className = "field-value mpd-direction " + dirClass;

        document.getElementById("mpdSequence").textContent = state.mpdSequence || "—";
        document.getElementById("mpdBias").textContent = state.mpdBias || "—";

        document.getElementById("mpdSequenceNote").textContent =
            state.sequenceNote || "Sequence engine synced.";
        document.getElementById("mpdBiasNote").textContent =
            state.biasNote || "Bias overlay stable.";

        // Pill
        const mpdPill = document.getElementById("mpdPill");
        mpdPill.className = "pill";
        if (dirClass === "up") {
            mpdPill.classList.add("pill--up");
            mpdPill.innerHTML = '<span class="pill-dot"></span>Flow Up';
        } else if (dirClass === "down") {
            mpdPill.classList.add("pill--down");
            mpdPill.innerHTML = '<span class="pill-dot"></span>Flow Down';
        } else {
            mpdPill.innerHTML = '<span class="pill-dot"></span>Flow Flat';
        }

        // Flow + Void badges
        const mode = state.flowMode || "Ultra Instinct";
        const voidOn = !!state.voidShield;
        const flowBadge = document.getElementById("flowModeBadge");
        const voidBadge = document.getElementById("voidBadge");
        flowBadge.textContent = mode;
        voidBadge.textContent = voidOn ? "Void Shield: On" : "Void Shield: Off";

        // Scores
        const pressureScore = typeof state.mpdScore === "number" ? state.mpdScore : null;
        document.getElementById("mpdPressureScore").textContent =
            pressureScore != null ? (pressureScore * 100).toFixed(0) + " %" : "—";
        document.getElementById("riskGateLabel").textContent = riskGateFromScore(pressureScore);

        // MTF stack
        updateMTFBias("bias4h", state.bias4h);
        updateMTFBias("bias1h", state.bias1h);
        updateMTFBias("bias30m", state.bias30m);
        updateMTFBias("bias15m", state.bias15m);

        const stackScore =
            typeof state.stackScore === "number" ? state.stackScore : pressureScore;
        document.getElementById("stackScoreLabel").textContent =
            stackScore != null ? (stackScore * 100).toFixed(0) + " %" : "—";
        document.getElementById("conflictLabel").textContent =
            stackConflictLabel(stackScore);

        // Phase
        const phase = phaseFromPayload(state);
        applyPhaseUI(phase.phaseTag, phase.phaseMode);

        // Last update label
        document.getElementById("lastUpdateLabel").textContent =
            "Last update: " + formatTime(state.timestamp || Date.now());
    }

    // ========= HISTORY / TREND ARC =========
    function renderHistory() {
        const svg = document.getElementById("historySvg");
        const pathEl = document.getElementById("historyPath");
        const emptyLabel = document.getElementById("historyEmpty");
        const meta = document.getElementById("historyMeta");

        // Clear dots
        const oldDots = svg.querySelectorAll(".history-dot");
        oldDots.forEach(d => d.remove());

        if (history.length < 2) {
            pathEl.setAttribute("d", "");
            emptyLabel.style.display = "block";
            meta.textContent = "Need at least 2 packets to form an arc.";
            return;
        }

        emptyLabel.style.display = "none";

        const width = svg.clientWidth || 300;
        const height = svg.clientHeight || 60;
        const topPadding = 6;
        const bottomPadding = 6;

        let min = 1;
        let max = 0;
        for (const h of history) {
            const v = typeof h.mpdScore === "number" ? h.mpdScore : 0.5;
            if (v < min) min = v;
            if (v > max) max = v;
        }
        if (max === min) {
            max = min + 0.0001;
        }

        const n = history.length;
        const stepX = n > 1 ? width / (n - 1) : width;
        const usableHeight = height - topPadding - bottomPadding;

        let d = "";
        history.forEach((h, i) => {
            const v = typeof h.mpdScore === "number" ? h.mpdScore : 0.5;
            const norm = (v - min) / (max - min); // 0–1
            const x = i * stepX;
            const y = height - bottomPadding - norm * usableHeight;

            if (i === 0) {
                d += `M ${x},${y}`;
            } else {
                const prevX = (i - 1) * stepX;
                const midX = (prevX + x) / 2;
                // Simple curve using quadratic commands
                d += ` Q ${midX},${y} ${x},${y}`;
            }

            // Dots
            const dot = document.createElementNS("http://www.w3.org/2000/svg", "circle");
            dot.setAttribute("cx", x);
            dot.setAttribute("cy", y);
            dot.setAttribute("r", 2.6);
            const dirClass = classifyDirection(h.mpdDirection);
            dot.setAttribute(
                "class",
                "history-dot " + (dirClass === "down" ? "down" : "")
            );
            svg.appendChild(dot);
        });

        pathEl.setAttribute("d", d);

        const first = history[0];
        const last = history[history.length - 1];
        const delta = ((last.mpdScore - first.mpdScore) * 100).toFixed(1);
        meta.textContent =
            "Arc: " +
            formatTime(first.timestamp) +
            " → " +
            formatTime(last.timestamp) +
            " · Δ " +
            delta +
            " pts";
    }

    function pushHistoryPacket(packet) {
        history.push(packet);
        if (history.length > MAX_HISTORY) {
            history.splice(0, history.length - MAX_HISTORY);
        }
        renderHistory();
    }

    // ========= BACKEND POLLING =========
    async function fetchLatestState() {
        if (demoMode) {
            runDemoTick();
            return;
        }
        try {
            const res = await fetch(BACKEND_URL + "/state/latest", {
                cache: "no-store"
            });
            if (!res.ok) throw new Error("HTTP " + res.status);
            const data = await res.json();

            const packet = {
                timestamp: data.timestamp || Date.now(),
                mpdDirection: data.mpdDirection,
                mpdSequence: data.mpdSequence,
                mpdBias: data.mpdBias,
                mpdScore:
                    typeof data.mpdScore === "number"
                        ? data.mpdScore
                        : typeof data.strength === "number"
                        ? data.strength
                        : 0.5,
                flowMode: data.flowMode,
                voidShield: data.voidShield,
                bias4h: data.bias4h,
                bias1h: data.bias1h,
                bias30m: data.bias30m,
                bias15m: data.bias15m,
                stackScore: data.stackScore,
                phaseTag: data.phaseTag,
                phaseMode: data.phaseMode,
                sequenceNote: data.sequenceNote,
                biasNote: data.biasNote
            };

            updateUIFromState(packet);
            pushHistoryPacket(packet);
        } catch (e) {
            console.warn("Backend unreachable, switching to demo mode.", e);
            demoMode = true;
            runDemoTick();
        }
    }

    function runDemoTick() {
        // Very simple synthetic ticker so UI isn't blank before backend exists
        demoTick++;
        const t = Date.now();
        const base = 0.5 + 0.3 * Math.sin(demoTick / 4);
        const direction = base > 0.5 ? "STRONG UP" : base < 0.5 ? "STRONG DOWN" : "FLAT";

        const packet = {
            timestamp: t,
            mpdDirection: direction,
            mpdSequence: base > 0.5 ? "HTC Up" : "Decay / Coil",
            mpdBias: base > 0.5 ? "Normal | Bullish" : "Fade | Bearish",
            mpdScore: Math.max(0, Math.min(1, base)),
            flowMode: base > 0.6 ? "Ultra Instinct" : base < 0.4 ? "Kaio-Ken" : "SSBlue",
            voidShield: base < 0.35,
            bias4h: base > 0.55 ? "Bullish" : "Neutral",
            bias1h: base > 0.55 ? "Bullish" : base < 0.45 ? "Bearish" : "Neutral",
            bias30m: base > 0.5 ? "Bullish" : "Bearish",
            bias15m: base > 0.5 ? "Bullish" : "Bearish",
            stackScore: Math.max(0, Math.min(1, 0.6 + 0.25 * Math.cos(demoTick / 5))),
            phaseTag: base < 0.35 ? "Void" : base > 0.65 ? "Coherence" : "Transition",
            phaseMode: base > 0.5 ? "Bull" : "Bear"
        };

        updateUIFromState(packet);
        pushHistoryPacket(packet);
    }

    // ========= INIT =========
    document.getElementById("refreshBtn").addEventListener("click", () => {
        demoMode = false; // try backend again
        fetchLatestState();
    });

    // Initial immediate fetch, then interval
    fetchLatestState();
    setInterval(fetchLatestState, POLL_INTERVAL);
</script>
</body>
</html>