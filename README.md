[index.html](https://github.com/user-attachments/files/30074599/index.html)
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>OEC Weekly Incentive</title>
        <style>
:root {
  --ink: #172033;
  --muted: #667085;
  --line: #d8dee8;
  --background: #f4f6f8;
  --panel: #ffffff;
  --teal: #087f8c;
  --teal-dark: #076571;
  --teal-soft: #e5f5f4;
  --green: #147d64;
  --green-soft: #e8f6f0;
  --amber: #9b6200;
  --amber-soft: #fff4d8;
  --red: #b42318;
  --red-soft: #fff0ee;
}

* { box-sizing: border-box; }
[hidden] { display: none !important; }

body {
  margin: 0;
  color: var(--ink);
  background: var(--background);
  font-family: Inter, Arial, sans-serif;
  font-size: 14px;
  letter-spacing: 0;
}

button, input, select { font: inherit; }
button { cursor: pointer; }

.topbar {
  min-height: 78px;
  padding: 14px max(24px, calc((100vw - 1480px) / 2));
  background: #fff;
  border-bottom: 1px solid var(--line);
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
}

.eyebrow {
  margin: 0 0 3px;
  color: var(--teal);
  font-size: 11px;
  font-weight: 700;
}

h1 { margin: 0; font-size: 24px; }
h2 { margin: 0; font-size: 16px; }

.top-actions { display: flex; align-items: center; gap: 12px; }
.status-dot { color: var(--muted); font-size: 12px; }
.status-dot::before {
  content: "";
  display: inline-block;
  width: 8px;
  height: 8px;
  margin-right: 7px;
  border-radius: 50%;
  background: #98a2b3;
}
.status-dot.ready::before { background: var(--green); }

.icon-button {
  width: 38px;
  height: 38px;
  display: grid;
  place-items: center;
  border: 1px solid var(--line);
  border-radius: 7px;
  background: #fff;
}
.icon-button:disabled { opacity: .45; cursor: default; }

svg {
  width: 18px;
  height: 18px;
  fill: none;
  stroke: currentColor;
  stroke-width: 1.8;
  stroke-linecap: round;
  stroke-linejoin: round;
}

main {
  width: min(1480px, calc(100% - 32px));
  margin: 18px auto 36px;
}

.tabs {
  display: flex;
  gap: 8px;
  margin-bottom: 12px;
  border-bottom: 1px solid var(--line);
}
.tab-button {
  min-height: 40px;
  padding: 0 14px;
  border: 1px solid transparent;
  border-bottom: 0;
  border-radius: 7px 7px 0 0;
  background: transparent;
  color: var(--muted);
  font-weight: 700;
}
.tab-button.active {
  background: #fff;
  color: var(--teal);
  border-color: var(--line);
}
.tab-panel { display: none; }
.tab-panel.active { display: block; }

.control-band {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 46px minmax(260px, .34fr);
  align-items: center;
  gap: 18px;
  padding: 18px;
  background: #fff;
  border: 1px solid var(--line);
  border-radius: 8px;
}

label {
  display: block;
  margin-bottom: 7px;
  color: #344054;
  font-size: 12px;
  font-weight: 600;
}

.input-row { display: flex; gap: 9px; }
input, select {
  height: 40px;
  border: 1px solid #cfd6df;
  border-radius: 7px;
  background: #fff;
  color: var(--ink);
  padding: 0 11px;
  outline: none;
}
input:focus, select:focus { border-color: var(--teal); box-shadow: 0 0 0 3px rgba(8,127,140,.10); }
.input-row input { flex: 1; min-width: 0; }

.primary-button, .secondary-button {
  min-height: 40px;
  border-radius: 7px;
  padding: 0 14px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-weight: 600;
  white-space: nowrap;
}
.primary-button { border: 1px solid var(--teal); background: var(--teal); color: #fff; }
.primary-button:hover { background: var(--teal-dark); }
.secondary-button { width: 100%; border: 1px solid var(--line); background: #fff; color: #344054; }
.source-note { margin: 7px 0 0; color: var(--muted); font-size: 11px; }

.divider { height: 58px; border-left: 1px solid var(--line); position: relative; }
.divider span {
  position: absolute;
  top: 18px;
  left: -15px;
  padding: 3px 7px;
  background: #fff;
  color: #98a2b3;
  font-size: 10px;
}

.rules-strip {
  margin-top: 12px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  background: #fff;
  border: 1px solid var(--line);
  border-radius: 8px;
  overflow: hidden;
}
.rules-strip div { padding: 13px 16px; border-right: 1px solid var(--line); }
.rules-strip div:last-child { border-right: 0; }
.rules-strip span { display: block; color: var(--muted); font-size: 11px; }
.rules-strip strong { display: block; margin-top: 4px; font-size: 14px; }

.empty-state {
  min-height: 350px;
  display: grid;
  align-content: center;
  justify-items: center;
  text-align: center;
  color: var(--muted);
}
.empty-state h2 { margin-top: 14px; color: var(--ink); }
.empty-state p { max-width: 520px; margin: 8px 0; line-height: 1.6; }
.empty-icon {
  width: 48px;
  height: 48px;
  display: grid;
  place-items: center;
  color: var(--teal);
  background: var(--teal-soft);
  border-radius: 8px;
}

.dashboard { margin-top: 14px; }
.filters {
  display: flex;
  gap: 12px;
  align-items: end;
  margin-bottom: 12px;
}
.field { min-width: 190px; }
.field.grow { flex: 1; }
.field input, .field select { width: 100%; }

.kpi-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
  margin-bottom: 12px;
}
.kpi {
  min-height: 108px;
  padding: 15px;
  background: #fff;
  border: 1px solid var(--line);
  border-radius: 8px;
}
.kpi span { color: var(--muted); font-size: 11px; font-weight: 600; }
.kpi strong { display: block; margin-top: 10px; font-size: 23px; }
.kpi small { display: block; margin-top: 7px; color: var(--muted); font-size: 11px; }

.content-grid {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 350px;
  gap: 12px;
  align-items: start;
}
.table-panel, .detail-panel {
  background: #fff;
  border: 1px solid var(--line);
  border-radius: 8px;
}
.panel-heading {
  min-height: 65px;
  padding: 14px 16px;
  border-bottom: 1px solid var(--line);
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
}
.panel-heading p { margin: 5px 0 0; color: var(--muted); font-size: 11px; }
.count-chip { padding: 5px 8px; border-radius: 6px; background: #eef2f6; color: #475467; font-size: 11px; }

.table-wrap { max-height: 580px; overflow: auto; }
table { width: 100%; border-collapse: collapse; white-space: nowrap; }
th {
  position: sticky;
  top: 0;
  z-index: 1;
  padding: 10px 12px;
  background: #f8fafb;
  border-bottom: 1px solid var(--line);
  color: #667085;
  font-size: 10px;
  text-align: left;
  text-transform: uppercase;
}
td { padding: 11px 12px; border-bottom: 1px solid #edf0f3; font-size: 12px; }
tbody tr { cursor: pointer; }
tbody tr:hover, tbody tr.selected { background: #f0f8f8; }
.money, .number { text-align: right; font-variant-numeric: tabular-nums; }

.badge {
  display: inline-flex;
  align-items: center;
  min-height: 24px;
  padding: 3px 8px;
  border-radius: 6px;
  font-size: 10px;
  font-weight: 700;
}
.badge.eligible { background: var(--green-soft); color: var(--green); }
.badge.not-eligible { background: var(--amber-soft); color: var(--amber); }

.detail-panel { min-height: 300px; }
.detail-empty { padding: 36px 18px; color: var(--muted); text-align: center; font-size: 12px; }
.agent-head {
  padding: 16px;
  display: flex;
  justify-content: space-between;
  gap: 12px;
  align-items: flex-start;
  border-bottom: 1px solid var(--line);
}
.agent-head strong { display: block; font-size: 14px; }
.agent-head span:not(.badge) { display: block; margin-top: 5px; color: var(--muted); font-size: 11px; }
.progress-block { padding: 16px; border-bottom: 1px solid var(--line); }
.progress-block > div:first-child { display: flex; justify-content: space-between; font-size: 11px; }
.progress-track { height: 8px; margin: 10px 0 7px; overflow: hidden; border-radius: 4px; background: #e8ecef; }
.progress-track span { display: block; height: 100%; max-width: 100%; background: var(--teal); }
.progress-block small { color: var(--muted); font-size: 10px; }
.product-list { padding: 7px 16px 14px; }
.product-row {
  padding: 10px 0;
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 5px 12px;
  border-bottom: 1px solid #edf0f3;
}
.product-row:last-child { border-bottom: 0; }
.product-row strong { font-size: 11px; }
.product-row span { color: var(--muted); font-size: 10px; }
.product-row .product-money { grid-row: 1 / span 2; grid-column: 2; color: var(--ink); text-align: right; }

.toast {
  position: fixed;
  right: 20px;
  bottom: 20px;
  max-width: min(400px, calc(100% - 40px));
  padding: 11px 14px;
  border-radius: 7px;
  background: #172033;
  color: #fff;
  font-size: 12px;
  opacity: 0;
  transform: translateY(8px);
  pointer-events: none;
  transition: .2s ease;
}
.toast.show { opacity: 1; transform: translateY(0); }

.dodolan-filters { margin-top: 0; }
.dodolan-board {
  max-height: 680px;
  overflow: auto;
}
.leader-group {
  border-bottom: 1px solid var(--line);
}
.leader-group:last-child { border-bottom: 0; }
.leader-summary {
  position: sticky;
  top: 0;
  z-index: 2;
  min-height: 42px;
  padding: 9px 14px;
  display: grid;
  grid-template-columns: 24px minmax(220px, 1fr) 90px 150px;
  gap: 10px;
  align-items: center;
  background: #e8eef4;
  cursor: pointer;
}
.leader-toggle {
  width: 18px;
  height: 18px;
  display: grid;
  place-items: center;
  border: 1px solid #91a4b8;
  border-radius: 4px;
  background: #fff;
  color: #476176;
  font-weight: 700;
}
.leader-summary span {
  color: #475467;
  font-size: 11px;
  font-weight: 700;
  text-align: right;
}
.leader-group.collapsed .dodolan-table-wrap { display: none; }
.dodolan-table-wrap { overflow-x: auto; }
.dodolan-table th {
  top: 42px;
}
.dodolan-table td:nth-child(2) {
  min-width: 430px;
  max-width: 560px;
  white-space: normal;
}
.dodolan-table td:nth-child(3) {
  min-width: 260px;
  max-width: 420px;
  white-space: normal;
}
.package-dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin-right: 8px;
  border-radius: 2px;
  vertical-align: -1px;
}
.campaign-pill {
  display: inline-block;
  padding: 4px 7px;
  border-radius: 5px;
  line-height: 1.35;
}
.campaign-gold { background: #f6d66b; color: #533f00; }
.campaign-green { background: #95c77b; color: #123d1c; }
.campaign-purple { background: #bca8e8; color: #2e1f5e; }
.campaign-blue { background: #9fc4df; color: #143d59; }
.campaign-gray { background: #e4e7ec; color: #475467; }

@media (max-width: 980px) {
  .control-band { grid-template-columns: 1fr; }
  .divider { height: 1px; border-left: 0; border-top: 1px solid var(--line); }
  .divider span { top: -10px; left: calc(50% - 16px); }
  .rules-strip, .kpi-grid { grid-template-columns: repeat(2, 1fr); }
  .rules-strip div:nth-child(2) { border-right: 0; }
  .rules-strip div:nth-child(-n+2) { border-bottom: 1px solid var(--line); }
  .content-grid { grid-template-columns: 1fr; }
  .leader-summary { grid-template-columns: 24px minmax(140px, 1fr) 70px 120px; }
}

@media (max-width: 620px) {
  .topbar { padding: 13px 16px; }
  h1 { font-size: 20px; }
  main { width: min(100% - 20px, 1480px); margin-top: 10px; }
  .input-row, .filters { flex-direction: column; align-items: stretch; }
  .primary-button { width: 100%; }
  .field { min-width: 0; width: 100%; }
  .rules-strip, .kpi-grid { grid-template-columns: 1fr; }
  .rules-strip div { border-right: 0; border-bottom: 1px solid var(--line); }
  .rules-strip div:last-child { border-bottom: 0; }
  .kpi { min-height: 94px; }
  .top-actions .status-dot { display: none; }
}

</style>
</head>
<body>
  <header class="topbar">
    <div>
      <p class="eyebrow">OEC PERFORMANCE</p>
      <h1>Weekly Incentive</h1>
    </div>
    <div class="top-actions">
      <span id="dataStatus" class="status-dot">Belum ada data</span>
      <button id="exportButton" class="icon-button" type="button" title="Export hasil ke Excel" disabled>
        <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 3v12m0 0 4-4m-4 4-4-4M5 17v3h14v-3"/></svg>
      </button>
    </div>
  </header>

  <main>
    <nav class="tabs" aria-label="Dashboard sections">
      <button class="tab-button active" type="button" data-tab="incentivePanel">DS INCENTIVE ALL</button>
      <button class="tab-button" type="button" data-tab="dodolanPanel">DODOLAN</button>
    </nav>

    <section id="incentivePanel" class="tab-panel active">
    <section class="rules-strip">
      <div><span>Scope</span><strong>Layer 1</strong></div>
      <div><span>Target mingguan</span><strong>Rp23.400.000</strong></div>
      <div><span>W1 minimum TH</span><strong>50%</strong></div>
      <div><span>W2-W5 minimum TH</span><strong>40%</strong></div>
    </section>

    <section id="emptyState" class="empty-state">
      <div class="empty-icon">
        <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M4 19V9m6 10V5m6 14v-7m4 7H2"/></svg>
      </div>
      <h2>Muat raw transaksi untuk mulai</h2>
      <p>Dashboard akan menghitung revenue, pencapaian target, tier TH, dan incentive setiap agent Layer 1.</p>
    </section>

    <section id="dashboard" class="dashboard" hidden>
      <div class="filters">
        <div class="field">
          <label for="weekFilter">Week</label>
          <select id="weekFilter"></select>
        </div>
        <div class="field grow">
          <label for="searchFilter">Cari agent atau leader</label>
          <input id="searchFilter" type="search" placeholder="Ketik nama...">
        </div>
        <div class="field">
          <label for="statusFilter">Status</label>
          <select id="statusFilter">
            <option value="all">Semua</option>
            <option value="eligible">Cair</option>
            <option value="not-eligible">Belum cair</option>
          </select>
        </div>
      </div>

      <div class="kpi-grid">
        <article class="kpi"><span>Total revenue</span><strong id="revenueKpi">Rp0</strong><small id="revenueNote">0 agent</small></article>
        <article class="kpi"><span>Estimasi incentive</span><strong id="incentiveKpi">Rp0</strong><small id="incentiveNote">Berdasarkan rate produk</small></article>
        <article class="kpi"><span>Agent mencapai minimum</span><strong id="eligibleKpi">0</strong><small id="eligibleNote">TH minimum 40%</small></article>
        <article class="kpi"><span>Median TH</span><strong id="medianKpi">0%</strong><small>Target Rp23,4 juta / minggu</small></article>
      </div>

      <div class="content-grid">
        <section class="table-panel">
          <div class="panel-heading">
            <div>
              <h2>Incentive per agent</h2>
              <p id="tableCaption">Ringkasan per minggu</p>
            </div>
            <span id="rowCount" class="count-chip">0 agent</span>
          </div>
          <div class="table-wrap">
            <table>
              <thead>
                <tr>
                  <th>Agent</th>
                  <th>Leader</th>
                  <th>Revenue</th>
                  <th>TH</th>
                  <th>Tier</th>
                  <th>Incentive</th>
                  <th>Status</th>
                </tr>
              </thead>
              <tbody id="summaryBody"></tbody>
            </table>
          </div>
        </section>

        <aside class="detail-panel">
          <div class="panel-heading">
            <div>
              <h2>Detail agent</h2>
              <p>Klik baris agent untuk melihat produk</p>
            </div>
          </div>
          <div id="detailEmpty" class="detail-empty">Belum ada agent dipilih.</div>
          <div id="detailContent" hidden>
            <div class="agent-head">
              <div><strong id="detailName"></strong><span id="detailLeader"></span></div>
              <span id="detailStatus" class="badge"></span>
            </div>
            <div class="progress-block">
              <div><span>Pencapaian target</span><strong id="detailTh"></strong></div>
              <div class="progress-track"><span id="detailProgress"></span></div>
              <small id="detailRevenue"></small>
            </div>
            <div class="product-list" id="productList"></div>
          </div>
        </aside>
      </div>
    </section>
    </section>

    <section id="dodolanPanel" class="tab-panel">
      <div class="filters dodolan-filters">
        <div class="field">
          <label for="dodolanWeekFilter">Week</label>
          <select id="dodolanWeekFilter"></select>
        </div>
        <div class="field">
          <label for="dodolanLeaderFilter">Leader</label>
          <select id="dodolanLeaderFilter"></select>
        </div>
        <div class="field grow">
          <label for="dodolanSearchFilter">Cari package, campaign, agent</label>
          <input id="dodolanSearchFilter" type="search" placeholder="Ketik nama...">
        </div>
      </div>

      <div class="kpi-grid">
        <article class="kpi"><span>Total revenue</span><strong id="dodolanRevenueKpi">Rp0</strong><small id="dodolanRevenueNote">0 transaksi</small></article>
        <article class="kpi"><span>Total package</span><strong id="dodolanPackageKpi">0</strong><small>Package terjual</small></article>
        <article class="kpi"><span>Leader aktif</span><strong id="dodolanLeaderKpi">0</strong><small>Dalam filter aktif</small></article>
        <article class="kpi"><span>Agent aktif</span><strong id="dodolanAgentKpi">0</strong><small>Dalam filter aktif</small></article>
      </div>

      <section class="table-panel">
        <div class="panel-heading">
          <div>
            <h2>DODOLAN</h2>
            <p id="dodolanCaption">Penjualan paket per leader dan agent</p>
          </div>
          <span id="dodolanRowCount" class="count-chip">0 rows</span>
        </div>
        <div id="dodolanBoard" class="dodolan-board"></div>
      </section>
    </section>
  </main>

  <div id="toast" class="toast" role="status" aria-live="polite"></div>
  <script src="https://cdn.jsdelivr.net/npm/xlsx@0.18.5/dist/xlsx.full.min.js"></script>
  <script>
const WEEKLY_TARGET = 23400000;
const SOURCE_SHEET_ID = "1qyGghBZrdfeTVbBGQwqWWFSjK2J_uvhy4kbcCg2CY-c";
const WEEK_PERIODS = [
  { name: "W 1 JUL", weekNum: 27, minimum: 0.50, scheme: "W1" },
  { name: "W 2 JUL", weekNum: 28, minimum: 0.40, scheme: "W2" },
  { name: "W 3 JUL", weekNum: 29, minimum: 0.40, scheme: "W2" },
  { name: "W 4 JUL", weekNum: 30, minimum: 0.40, scheme: "W2" },
  { name: "W 5 JUL", weekNum: 31, minimum: 0.40, scheme: "W2" },
];

const RATES = {
  W1: {
    "BAC & Mathchamps Offline": { 0: 0, .5: .0215, .75: .0265, 1: .0475, 1.25: .055 },
    "BAON Elite": { 0: 0, .5: .024, .75: .0265, 1: .0535, 1.25: .06 },
    "BAON Prem": { 0: 0, .5: .0438, .75: .05, 1: .1135, 1.25: .135 },
    "BAON Reg": { 0: 0, .5: .037, .75: .0433, 1: .097, 1.25: .12 },
    "Others": { 0: 0, .5: .0155, .75: .0175, 1: .0188, 1.25: .0198 },
    "RB": { 0: 0, .5: .0383, .75: .045, 1: .1013, 1.25: .1275 },
    "RGP Offline": { 0: 0, .5: .003, .75: .005, 1: .01, 1.25: .01 },
    "Math Champs Online": { 0: 0, .5: .01, .75: .01, 1: .01, 1.25: .01 },
    "Skill Academy": { 0: 0, .5: .02, .75: .02, 1: .02, 1.25: .02 },
  },
  W2: {
    "BAC & Mathchamps Offline": { 0: 0, .4: .014, .5: .0215, .75: .0265, 1: .0475, 1.25: .055 },
    "BAON Elite": { 0: 0, .4: .0155, .5: .024, .75: .0265, 1: .0535, 1.25: .06 },
    "BAON Prem": { 0: 0, .4: .0285, .5: .0438, .75: .05, 1: .1135, 1.25: .135 },
    "BAON Reg": { 0: 0, .4: .024, .5: .037, .75: .0433, 1: .097, 1.25: .12 },
    "Others": { 0: 0, .4: .01, .5: .0155, .75: .0175, 1: .0188, 1.25: .0198 },
    "RB": { 0: 0, .4: .025, .5: .0383, .75: .045, 1: .1013, 1.25: .1275 },
    "RGP Offline": { 0: 0, .4: .002, .5: .003, .75: .005, 1: .01, 1.25: .01 },
    "Math Champs Online": { 0: 0, .4: .0065, .5: .01, .75: .01, 1: .01, 1.25: .01 },
    "Skill Academy": { 0: 0, .4: .013, .5: .02, .75: .02, 1: .02, 1.25: .02 },
  },
};

let summary = [];
let dodolanRows = [];
let selectedKey = "";

const el = id => document.getElementById(id);
const rupiah = value => new Intl.NumberFormat("id-ID", { style: "currency", currency: "IDR", maximumFractionDigits: 0 }).format(value || 0);
const percent = value => `${new Intl.NumberFormat("id-ID", { maximumFractionDigits: 1 }).format((value || 0) * 100)}%`;

function parseAmount(value) {
  if (typeof value === "number") return Number.isFinite(value) ? value : 0;
  const cleaned = String(value ?? "").replace(/[^\d-]/g, "");
  return cleaned ? Number(cleaned) : 0;
}

function parseDate(value) {
  if (value instanceof Date) return value;
  if (typeof value === "number") return new Date(Math.round((value - 25569) * 86400 * 1000));
  const date = new Date(value);
  return Number.isNaN(date.getTime()) ? null : date;
}

function normalizeWeekName(value) {
  return String(value || "").trim().replace(/\s+/g, " ").toUpperCase();
}

function weekFor(weekName, weekNum) {
  const normalizedName = normalizeWeekName(weekName);
  const normalizedNum = Number(weekNum);
  return WEEK_PERIODS.find(week => week.name === normalizedName && week.weekNum === normalizedNum) || null;
}

function productBucket(row) {
  const type = String(row.product_type || "").trim();
  const group = String(row.product_group || "").trim().toUpperCase();
  const lower = type.toLowerCase();
  if (lower.includes("elite")) return "BAON Elite";
  if (lower.includes("premium")) return "BAON Prem";
  if (lower.includes("regular")) return "BAON Reg";
  if (lower === "brain academy" || lower === "math champs") return "BAC & Mathchamps Offline";
  if (lower === "math champs online") return "Math Champs Online";
  if (lower === "ruangbelajar" || group === "RB") return "RB";
  if (lower === "ruangguru privat" || group === "RGP") return "RGP Offline";
  if (lower === "skill academy") return "Skill Academy";
  return "Others";
}

function normalizeRows(rows) {
  const keys = {};
  Object.keys(rows[0] || {}).forEach(key => { keys[key.trim().toLowerCase()] = key; });
  const read = (row, name) => row[keys[name.toLowerCase()]];
  return rows.map(row => ({
    date: parseDate(read(row, "Date")),
    weekName: normalizeWeekName(read(row, "Week name")),
    weekNum: Number(read(row, "WeekNum")),
    invoice: String(read(row, "invoice") || ""),
    agent: String(read(row, "agent_name") || "").trim(),
    leader: String(read(row, "leader_name") || "").trim(),
    packageName: String(read(row, "package_name") || "").trim(),
    campaign: String(read(row, "campaign") || "").trim(),
    team: String(read(row, "category team") || "").trim(),
    product_type: String(read(row, "product_type") || "").trim(),
    product_group: String(read(row, "product_group") || "").trim(),
    revenue: parseAmount(read(row, "amount")),
  })).filter(row => row.agent && row.team === "Layer 1" && weekFor(row.weekName, row.weekNum));
}

function buildDodolanRows(rows) {
  return rows.map(row => {
    const week = weekFor(row.weekName, row.weekNum);
    return {
      ...row,
      week: week.name,
      packageName: row.packageName || row.product_type || "-",
      campaign: row.campaign || "No Campaign",
      product: productBucket(row),
      txn: 1,
    };
  }).sort((a, b) =>
    a.week.localeCompare(b.week) ||
    a.leader.localeCompare(b.leader) ||
    a.packageName.localeCompare(b.packageName) ||
    b.revenue - a.revenue
  );
}

function chooseTier(th, week, product) {
  if (th < week.minimum) return 0;
  const tiers = Object.keys(RATES[week.scheme][product] || { 0: 0 }).map(Number).sort((a, b) => a - b);
  return tiers.reduce((chosen, tier) => tier <= th ? tier : chosen, 0);
}

function calculate(rows) {
  const agents = new Map();
  rows.forEach(row => {
    const week = weekFor(row.weekName, row.weekNum);
    const key = `${week.name}|${row.agent.toLowerCase()}`;
    if (!agents.has(key)) {
      agents.set(key, { key, week: week.name, weekMeta: week, agent: row.agent, leader: row.leader, revenue: 0, transactions: 0, products: {} });
    }
    const item = agents.get(key);
    const product = productBucket(row);
    item.revenue += row.revenue;
    item.transactions += row.invoice ? 1 : 0;
    item.products[product] = (item.products[product] || 0) + row.revenue;
  });

  return [...agents.values()].map(item => {
    item.th = item.revenue / WEEKLY_TARGET;
    item.eligible = item.th >= item.weekMeta.minimum;
    item.tier = chooseTier(item.th, item.weekMeta, Object.keys(item.products)[0] || "Others");
    item.productDetails = Object.entries(item.products).map(([product, revenue]) => {
      const tier = chooseTier(item.th, item.weekMeta, product);
      const rate = RATES[item.weekMeta.scheme][product]?.[tier] || 0;
      return { product, revenue, tier, rate, incentive: revenue * rate };
    }).sort((a, b) => b.revenue - a.revenue);
    item.incentive = item.productDetails.reduce((total, product) => total + product.incentive, 0);
    return item;
  }).sort((a, b) => a.week.localeCompare(b.week) || b.incentive - a.incentive || b.revenue - a.revenue);
}

async function loadWorkbook(buffer) {
  const workbook = XLSX.read(buffer, { type: "array", cellDates: true });
  const sheetName = workbook.SheetNames.find(name => name.trim().toUpperCase() === "RAW TRANSACTION") || workbook.SheetNames[0];
  const rows = XLSX.utils.sheet_to_json(workbook.Sheets[sheetName], { defval: "" });
  if (!rows.length) throw new Error("Sheet tidak memiliki data.");
  const normalized = normalizeRows(rows);
  summary = calculate(normalized);
  dodolanRows = buildDodolanRows(normalized);
  if (!summary.length) throw new Error("Tidak ada transaksi Layer 1 pada periode W1-W5 Juli.");
  prepareDashboard(sheetName, rows.length);
}

function prepareDashboard(sheetName, rawCount) {
  el("emptyState").hidden = true;
  el("dashboard").hidden = false;
  el("exportButton").disabled = false;
  el("dataStatus").textContent = `${rawCount.toLocaleString("id-ID")} raw rows`;
  el("dataStatus").classList.add("ready");
  const weeks = [...new Set(summary.map(row => row.week))];
  el("weekFilter").innerHTML = `<option value="all">Semua week</option>${weeks.map(week => `<option value="${week}">${week}</option>`).join("")}`;
  el("dodolanWeekFilter").innerHTML = `<option value="all">Semua week</option>${weeks.map(week => `<option value="${week}">${week}</option>`).join("")}`;
  const leaders = [...new Set(dodolanRows.map(row => row.leader || "-"))].sort((a, b) => a.localeCompare(b));
  el("dodolanLeaderFilter").innerHTML = `<option value="all">Semua leader</option>${leaders.map(leader => `<option value="${escapeHtml(leader)}">${escapeHtml(leader)}</option>`).join("")}`;
  showToast(`Data dari ${sheetName} berhasil dihitung.`);
  render();
  renderDodolan();
}

function aggregateAllWeeks(rows) {
  const availableWeeks = [...new Set(rows.map(row => row.week))];
  const agents = new Map();

  rows.forEach(row => {
    const key = row.agent.toLowerCase();
    if (!agents.has(key)) {
      agents.set(key, {
        key: `all|${key}`,
        week: "Semua Week",
        agent: row.agent,
        leader: row.leader,
        revenue: 0,
        incentive: 0,
        transactions: 0,
        eligibleWeeks: 0,
        products: {},
        allWeeks: true,
      });
    }

    const item = agents.get(key);
    item.revenue += row.revenue;
    item.incentive += row.incentive;
    item.transactions += row.transactions;
    item.eligibleWeeks += row.eligible ? 1 : 0;

    row.productDetails.forEach(product => {
      if (!item.products[product.product]) {
        item.products[product.product] = { product: product.product, revenue: 0, incentive: 0 };
      }
      item.products[product.product].revenue += product.revenue;
      item.products[product.product].incentive += product.incentive;
    });
  });

  return [...agents.values()].map(item => {
    item.target = WEEKLY_TARGET * availableWeeks.length;
    item.th = item.target ? item.revenue / item.target : 0;
    item.eligible = item.incentive > 0;
    item.tier = null;
    item.productDetails = Object.values(item.products).sort((a, b) => b.incentive - a.incentive);
    return item;
  }).sort((a, b) => b.incentive - a.incentive || b.revenue - a.revenue);
}

function filteredSummary() {
  const week = el("weekFilter").value;
  const query = el("searchFilter").value.trim().toLowerCase();
  const status = el("statusFilter").value;
  const baseRows = week === "all" ? aggregateAllWeeks(summary) : summary.filter(row => row.week === week);
  return baseRows.filter(row =>
    (!query || `${row.agent} ${row.leader}`.toLowerCase().includes(query)) &&
    (status === "all" || (status === "eligible") === row.eligible)
  );
}

function render() {
  const rows = filteredSummary();
  const totalRevenue = rows.reduce((sum, row) => sum + row.revenue, 0);
  const totalIncentive = rows.reduce((sum, row) => sum + row.incentive, 0);
  const eligible = rows.filter(row => row.eligible).length;
  const thValues = rows.map(row => row.th).sort((a, b) => a - b);
  const median = thValues.length ? thValues[Math.floor(thValues.length / 2)] : 0;
  const selectedWeek = el("weekFilter").value;
  const minimum = selectedWeek === "W 1 JUL" ? .5 : .4;

  el("revenueKpi").textContent = rupiah(totalRevenue);
  el("revenueNote").textContent = `${rows.length} agent`;
  el("incentiveKpi").textContent = rupiah(totalIncentive);
  el("eligibleKpi").textContent = eligible.toLocaleString("id-ID");
  el("eligibleNote").textContent = selectedWeek === "all" ? "Memiliki incentive pada minimal 1 week" : `TH minimum ${percent(minimum)}`;
  el("medianKpi").textContent = percent(median);
  el("rowCount").textContent = `${rows.length} agent`;
  el("tableCaption").textContent = selectedWeek === "all" ? "Total akumulasi seluruh week yang tersedia" : `${selectedWeek} · target Rp23.400.000`;

  el("summaryBody").innerHTML = rows.map(row => `
    <tr data-key="${row.key}" class="${row.key === selectedKey ? "selected" : ""}">
      <td><strong>${escapeHtml(row.agent)}</strong></td>
      <td>${escapeHtml(row.leader || "-")}</td>
      <td class="money">${rupiah(row.revenue)}</td>
      <td class="number">${percent(row.th)}</td>
      <td class="number">${row.allWeeks ? "Per week" : row.tier ? percent(row.tier) : "-"}</td>
      <td class="money"><strong>${rupiah(row.incentive)}</strong></td>
      <td><span class="badge ${row.eligible ? "eligible" : "not-eligible"}">${row.eligible ? "CAIR" : "BELUM CAIR"}</span></td>
    </tr>
  `).join("");

  document.querySelectorAll("#summaryBody tr").forEach(row => row.addEventListener("click", () => selectAgent(row.dataset.key)));
  if (selectedKey && !rows.some(row => row.key === selectedKey)) clearDetail();
}

function filteredDodolanRows() {
  const week = el("dodolanWeekFilter").value;
  const leader = el("dodolanLeaderFilter").value;
  const query = el("dodolanSearchFilter").value.trim().toLowerCase();
  return dodolanRows.filter(row =>
    (week === "all" || row.week === week) &&
    (leader === "all" || (row.leader || "-") === leader) &&
    (!query || `${row.packageName} ${row.campaign} ${row.agent} ${row.leader}`.toLowerCase().includes(query))
  );
}

function campaignClass(value) {
  const text = String(value || "").toLowerCase();
  if (text.includes("early") || text.includes("bird")) return "campaign-gold";
  if (text.includes("renewal") || text.includes("perpanjang")) return "campaign-purple";
  if (text.includes("special") || text.includes("reassign")) return "campaign-blue";
  if (text.includes("no campaign")) return "campaign-gray";
  return "campaign-green";
}

function renderDodolan() {
  const rows = filteredDodolanRows();
  const totalRevenue = rows.reduce((sum, row) => sum + row.revenue, 0);
  const leaders = new Set(rows.map(row => row.leader || "-"));
  const agents = new Set(rows.map(row => row.agent));

  el("dodolanRevenueKpi").textContent = rupiah(totalRevenue);
  el("dodolanRevenueNote").textContent = `${rows.length.toLocaleString("id-ID")} transaksi`;
  el("dodolanPackageKpi").textContent = rows.length.toLocaleString("id-ID");
  el("dodolanLeaderKpi").textContent = leaders.size.toLocaleString("id-ID");
  el("dodolanAgentKpi").textContent = agents.size.toLocaleString("id-ID");
  el("dodolanRowCount").textContent = `${rows.length.toLocaleString("id-ID")} rows`;
  el("dodolanCaption").textContent = el("dodolanWeekFilter").value === "all" ? "Penjualan paket seluruh week" : `Penjualan paket ${el("dodolanWeekFilter").value}`;

  const byLeader = new Map();
  rows.forEach(row => {
    const leader = row.leader || "-";
    if (!byLeader.has(leader)) byLeader.set(leader, []);
    byLeader.get(leader).push(row);
  });

  el("dodolanBoard").innerHTML = [...byLeader.entries()].map(([leader, leaderRows]) => {
    const leaderRevenue = leaderRows.reduce((sum, row) => sum + row.revenue, 0);
    return `
      <section class="leader-group">
        <div class="leader-summary">
          <button class="leader-toggle" type="button" aria-label="Toggle leader">-</button>
          <strong>${escapeHtml(leader)}</strong>
          <span>${leaderRows.length.toLocaleString("id-ID")} TXN</span>
          <span>${rupiah(leaderRevenue)}</span>
        </div>
        <div class="dodolan-table-wrap">
          <table class="dodolan-table">
            <thead>
              <tr>
                <th>Week</th>
                <th>Package Name</th>
                <th>Campaign</th>
                <th>Agent Name</th>
                <th>TXN</th>
                <th>Revenue</th>
              </tr>
            </thead>
            <tbody>
              ${leaderRows.map(row => `
                <tr>
                  <td>${escapeHtml(row.week)}</td>
                  <td><span class="package-dot ${campaignClass(row.campaign)}"></span>${escapeHtml(row.packageName)}</td>
                  <td><span class="campaign-pill ${campaignClass(row.campaign)}">${escapeHtml(row.campaign)}</span></td>
                  <td>${escapeHtml(row.agent)}</td>
                  <td class="number">${row.txn}</td>
                  <td class="money">${rupiah(row.revenue)}</td>
                </tr>
              `).join("")}
            </tbody>
          </table>
        </div>
      </section>
    `;
  }).join("") || `<div class="detail-empty">Tidak ada data pada filter ini.</div>`;

  document.querySelectorAll(".leader-summary").forEach(summary => {
    summary.addEventListener("click", () => {
      const group = summary.closest(".leader-group");
      group.classList.toggle("collapsed");
      summary.querySelector(".leader-toggle").textContent = group.classList.contains("collapsed") ? "+" : "-";
    });
  });
}

function selectAgent(key) {
  selectedKey = key;
  const selectedWeek = el("weekFilter").value;
  const sourceRows = selectedWeek === "all" ? aggregateAllWeeks(summary) : summary;
  const row = sourceRows.find(item => item.key === key);
  if (!row) return;
  el("detailEmpty").hidden = true;
  el("detailContent").hidden = false;
  el("detailName").textContent = row.agent;
  el("detailLeader").textContent = `${row.leader || "Tanpa leader"} · ${row.week}`;
  el("detailStatus").textContent = row.eligible ? "CAIR" : "BELUM CAIR";
  el("detailStatus").className = `badge ${row.eligible ? "eligible" : "not-eligible"}`;
  el("detailTh").textContent = percent(row.th);
  el("detailProgress").style.width = `${Math.min(row.th * 100, 100)}%`;
  el("detailRevenue").textContent = `${rupiah(row.revenue)} dari target ${rupiah(row.target || WEEKLY_TARGET)}`;
  el("productList").innerHTML = row.productDetails.map(product => `
    <div class="product-row">
      <strong>${escapeHtml(product.product)}</strong>
      <span>${row.allWeeks ? "Akumulasi rate dan tier tiap week" : `${percent(product.rate)} rate · tier ${product.tier ? percent(product.tier) : "-"}`}</span>
      <div class="product-money"><strong>${rupiah(product.incentive)}</strong><span>${rupiah(product.revenue)}</span></div>
    </div>
  `).join("");
  render();
}

function clearDetail() {
  selectedKey = "";
  el("detailEmpty").hidden = false;
  el("detailContent").hidden = true;
}

function escapeHtml(value) {
  return String(value).replace(/[&<>"']/g, char => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[char]));
}

function showToast(message) {
  el("toast").textContent = message;
  el("toast").classList.add("show");
  clearTimeout(showToast.timer);
  showToast.timer = setTimeout(() => el("toast").classList.remove("show"), 3200);
}

async function loadFromGoogleSheet() {
  el("dataStatus").textContent = "Memuat data...";
  try {
    const response = await fetch(
      `https://docs.google.com/spreadsheets/d/${SOURCE_SHEET_ID}/export?format=xlsx&_=${Date.now()}`,
      { cache: "no-store" }
    );
    if (!response.ok) throw new Error("Google Sheet tidak dapat diakses. Pastikan link dibuka untuk publik.");
    await loadWorkbook(await response.arrayBuffer());
  } catch (error) {
    el("dataStatus").textContent = "Gagal memuat data";
    showToast(error.message);
  }
}

function exportResults() {
  const rows = summary.map(row => ({
    "Week": row.week,
    "Agent": row.agent,
    "Leader": row.leader,
    "Target": WEEKLY_TARGET,
    "Revenue": row.revenue,
    "TH": row.th,
    "Tier TH": row.tier,
    "Incentive": row.incentive,
    "Status": row.eligible ? "CAIR" : "BELUM CAIR",
  }));
  const detailRows = summary.flatMap(row => row.productDetails.map(product => ({
    "Week": row.week,
    "Agent": row.agent,
    "Leader": row.leader,
    "Product": product.product,
    "Revenue": product.revenue,
    "TH Agent": row.th,
    "Tier": product.tier,
    "Rate": product.rate,
    "Incentive": product.incentive,
  })));
  const workbook = XLSX.utils.book_new();
  XLSX.utils.book_append_sheet(workbook, XLSX.utils.json_to_sheet(rows), "Summary Agent Week");
  XLSX.utils.book_append_sheet(workbook, XLSX.utils.json_to_sheet(detailRows), "Detail Product");
  XLSX.writeFile(workbook, `oec_layer1_incentive_${new Date().toISOString().slice(0, 10)}.xlsx`);
}

function switchTab(tabId) {
  document.querySelectorAll(".tab-button").forEach(button => button.classList.toggle("active", button.dataset.tab === tabId));
  document.querySelectorAll(".tab-panel").forEach(panel => panel.classList.toggle("active", panel.id === tabId));
}

document.querySelectorAll(".tab-button").forEach(button => button.addEventListener("click", () => switchTab(button.dataset.tab)));
el("weekFilter").addEventListener("change", render);
el("searchFilter").addEventListener("input", render);
el("statusFilter").addEventListener("change", render);
el("dodolanWeekFilter").addEventListener("change", renderDodolan);
el("dodolanLeaderFilter").addEventListener("change", renderDodolan);
el("dodolanSearchFilter").addEventListener("input", renderDodolan);
el("exportButton").addEventListener("click", exportResults);
loadFromGoogleSheet();

</script>
</body>
</html>
