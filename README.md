<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bible Reading Plan — Proverbs & Psalms (ASV)</title>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --color-background-primary: #ffffff;
    --color-background-secondary: #f5f5f3;
    --color-text-primary: #1a1a18;
    --color-text-secondary: #6b6b65;
    --color-text-tertiary: #9a9a93;
    --color-border-tertiary: rgba(0,0,0,0.1);
    --color-border-secondary: rgba(0,0,0,0.2);
    --color-border-primary: rgba(0,0,0,0.35);
    --font-sans: system-ui, -apple-system, sans-serif;
    --border-radius-md: 8px;
    --border-radius-lg: 12px;
    --amber: #BA7517;
  }
  @media (prefers-color-scheme: dark) {
    :root {
      --color-background-primary: #1e1e1c;
      --color-background-secondary: #2a2a28;
      --color-text-primary: #f0ede6;
      --color-text-secondary: #a0a099;
      --color-text-tertiary: #6e6e68;
      --color-border-tertiary: rgba(255,255,255,0.08);
      --color-border-secondary: rgba(255,255,255,0.15);
      --color-border-primary: rgba(255,255,255,0.28);
    }
  }
  body {
    font-family: var(--font-sans);
    background: var(--color-background-secondary);
    color: var(--color-text-primary);
    min-height: 100vh;
    padding: 2rem 1rem 4rem;
  }
  .wrapper {
    max-width: 680px;
    margin: 0 auto;
  }
  h1 {
    font-size: 1.5rem;
    font-weight: 500;
    color: var(--color-text-primary);
    margin-bottom: 4px;
  }
  .tagline {
    font-size: 13px;
    color: var(--color-text-secondary);
    margin-bottom: 1.5rem;
  }
  .controls {
    display: flex;
    gap: 10px;
    align-items: center;
    flex-wrap: wrap;
    margin-bottom: 1.25rem;
  }
  .controls label { font-size: 13px; color: var(--color-text-secondary); }
  select {
    font-size: 13px;
    padding: 6px 10px;
    border-radius: var(--border-radius-md);
    border: 0.5px solid var(--color-border-secondary);
    background: var(--color-background-primary);
    color: var(--color-text-primary);
  }
  .stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    margin-bottom: 1.25rem;
  }
  .stat {
    background: var(--color-background-primary);
    border-radius: var(--border-radius-md);
    padding: 12px 14px;
    border: 0.5px solid var(--color-border-tertiary);
  }
  .stat-label { font-size: 12px; color: var(--color-text-secondary); margin-bottom: 4px; }
  .stat-val { font-size: 20px; font-weight: 500; color: var(--color-text-primary); }
  .progress-bar {
    height: 5px;
    border-radius: 99px;
    background: var(--color-border-tertiary);
    margin-bottom: 1.5rem;
    overflow: hidden;
  }
  .progress-fill {
    height: 100%;
    border-radius: 99px;
    background: var(--amber);
    transition: width 0.3s;
  }
  .day-grid { display: flex; flex-direction: column; gap: 6px; }
  .day-row {
    display: grid;
    grid-template-columns: 32px 1fr 1fr 56px;
    align-items: center;
    gap: 10px;
    padding: 9px 12px;
    border-radius: var(--border-radius-md);
    border: 0.5px solid var(--color-border-tertiary);
    background: var(--color-background-primary);
    transition: background 0.15s;
  }
  .day-row.done {
    background: var(--color-background-secondary);
    border-color: transparent;
  }
  .day-row.today {
    box-shadow: 0 0 0 2px rgba(186,117,23,0.08) inset, 0 6px 18px rgba(0,0,0,0.06);
  }
  .day-num { font-size: 12px; color: var(--color-text-tertiary); font-weight: 500; text-align: center; }
  .ref { font-size: 13px; color: var(--color-text-primary); }
  .ref span { font-size: 11px; color: var(--color-text-secondary); display: block; margin-top: 1px; }
  .day-row.done .ref { color: var(--color-text-secondary); }
  .check-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 28px;
    height: 28px;
    border-radius: 50%;
    border: 1.5px solid var(--color-border-secondary);
    background: transparent;
    cursor: pointer;
    transition: all 0.15s;
    justify-self: end;
  }
  .check-btn:hover { border-color: var(--amber); }
  .check-btn.checked { background: #BA7517; border-color: #BA7517; }
  .check-icon {
    width: 13px; height: 13px;
    fill: none;
    stroke: var(--color-text-tertiary);
    stroke-width: 2;
    stroke-linecap: round;
    stroke-linejoin: round;
  }
  .check-btn.checked .check-icon { stroke: white; }
  .reset-btn {
    font-size: 12px;
    color: var(--color-text-secondary);
    background: none;
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: var(--border-radius-md);
    padding: 5px 12px;
    cursor: pointer;
    margin-left: auto;
  }
  .reset-btn:hover { border-color: var(--color-border-primary); color: var(--color-text-primary); }
  .month-label {
    font-size: 11px;
    color: var(--color-text-tertiary);
    text-align: center;
    padding: 4px 0;
    letter-spacing: 0.06em;
  }
  .site-footer {
    margin-top: 18px;
    padding: 12px;
    text-align: center;
    font-size: 13px;
    color: var(--color-text-secondary);
  }
  .site-footer a { color: var(--amber); text-decoration: none; }
</style>
</head>
<body>
<div class="wrapper">
  <h1>Proverbs & Psalms Reading Plan</h1>
  <p class="tagline">ASV · Monthly checklist · 1 Proverb/day + Psalms spread across the month</p>

  <div class="controls">
    <label>Month:</label>
    <select id="monthSel" onchange="render()">
      <option value="0">January</option><option value="1">February</option>
      <option value="2">March</option><option value="3">April</option>
      <option value="4">May</option><option value="5">June</option>
      <option value="6">July</option><option value="7">August</option>
      <option value="8">September</option><option value="9">October</option>
      <option value="10">November</option><option value="11">December</option>
    </select>
    <label>Year:</label>
    <select id="yearSel" onchange="render()">
      <option value="2025">2025</option>
      <option value="2026" selected>2026</option>
      <option value="2027">2027</option>
    </select>
    <label style="display:flex;align-items:center;gap:8px;font-size:13px;color:var(--color-text-secondary);">
      <input id="autoScroll" type="checkbox" style="width:16px;height:16px;" /> Auto-scroll to today
    </label>
    <button class="reset-btn" onclick="resetMonth()">Reset month</button>
    <button class="reset-btn" onclick="exportMonth()" title="Export current month JSON">Export</button>
    <label class="reset-btn" for="importFile" style="cursor:pointer;">Import</label>
    <input id="importFile" type="file" accept="application/json" style="display:none" onchange="importMonth(event)">
  </div>

  <div class="stats">
    <div class="stat"><div class="stat-label">Days done</div><div class="stat-val" id="sDone">0</div></div>
    <div class="stat"><div class="stat-label">Days left</div><div class="stat-val" id="sLeft">0</div></div>
    <div class="stat"><div class="stat-label">Completed</div><div class="stat-val" id="sPct">0%</div></div>
  </div>
  <div class="progress-bar"><div class="progress-fill" id="pBar" style="width:0%"></div></div>

  <div class="day-grid" id="grid"></div>
  <div id="notePanel" style="position:fixed;left:50%;transform:translateX(-50%);bottom:18px;width:640px;max-width:94%;background:var(--color-background-primary);border:0.5px solid var(--color-border-tertiary);border-radius:10px;padding:10px 12px;display:none;box-shadow:0 8px 20px rgba(0,0,0,0.08);">
    <div style="display:flex;align-items:center;gap:10px;margin-bottom:6px;">
      <div style="font-size:13px;color:var(--color-text-secondary);">Note for</div>
      <div id="noteDate" style="font-weight:600"></div>
      <div style="margin-left:auto;display:flex;gap:8px;align-items:center;">
        <button class="reset-btn" onclick="closeNote()">Close</button>
      </div>
    </div>
    <textarea id="noteText" rows="4" style="width:100%;padding:8px;border-radius:8px;border:0.5px solid var(--color-border-tertiary);resize:vertical;background:var(--color-background-secondary);"></textarea>
    <div style="display:flex;gap:8px;margin-top:8px;justify-content:flex-end;">
      <button class="reset-btn" onclick="saveNote()">Save Note</button>
      <button class="reset-btn" onclick="deleteNote()">Delete Note</button>
    </div>
  </div>
  <div class="site-footer">© 2026 <a href="https://github.com/EE2506" target="_blank" rel="noopener">EE2506</a> — Open source, free to use.</div>
</div>

<script>
const MONTHS = ['January','February','March','April','May','June','July','August','September','October','November','December'];
const now = new Date();
document.getElementById('monthSel').value = now.getMonth();

function daysInMonth(m, y) { return new Date(y, m+1, 0).getDate(); }

function buildPsalmsForMonth(days) {
  const total = 150;
  const perDay = [];
  let psalm = 1;
  for (let d = 0; d < days; d++) {
    const remaining = days - d;
    const psalmsLeft = total - psalm + 1;
    const count = Math.round(psalmsLeft / remaining);
    const end = Math.min(psalm + count - 1, 150);
    perDay.push({ start: psalm, end });
    psalm = end + 1;
    if (psalm > 150) psalm = 150;
  }
  return perDay;
}

function storageKey(m, y) { return 'bplan_' + y + '_' + m; }

function getMonthData(m, y) {
  try {
    const raw = localStorage.getItem(storageKey(m, y));
    if (!raw) return {};
    const parsed = JSON.parse(raw);
    const normalized = {};
    for (const k in parsed) {
      const val = parsed[k];
      if (typeof val === 'boolean') normalized[k] = { done: val, note: '' };
      else if (val && typeof val === 'object') normalized[k] = { done: !!val.done, note: val.note || '' };
      else normalized[k] = { done: !!val, note: '' };
    }
    return normalized;
  } catch (e) { return {}; }
}

function saveMonthData(m, y, data) {
  try { localStorage.setItem(storageKey(m, y), JSON.stringify(data)); } catch (e) {}
}

let monthData = {};
let selected = null;

function render() {
  const m = parseInt(document.getElementById('monthSel').value);
  const y = parseInt(document.getElementById('yearSel').value);
  const days = daysInMonth(m, y);
  monthData = getMonthData(m, y);
  const psalms = buildPsalmsForMonth(days);
  const grid = document.getElementById('grid');
  grid.innerHTML = '';

  const label = document.createElement('div');
  label.className = 'month-label';
  label.textContent = MONTHS[m] + ' ' + y + ' — ASV';
  grid.appendChild(label);

  for (let d = 0; d < days; d++) {
    const day = d + 1;
    const entry = monthData[day] || { done: false, note: '' };
    const isDone = !!entry.done;
    const ps = psalms[d];
    const psLabel = ps.start === ps.end ? 'Psalm ' + ps.start : 'Psalms ' + ps.start + '–' + ps.end;

    const row = document.createElement('div');
    row.className = 'day-row' + (isDone ? ' done' : '');
    row.dataset.day = day;
    if (m === now.getMonth() && y === now.getFullYear() && day === now.getDate()) row.className += ' today';
    row.innerHTML =
      '<div class="day-num">' + day + '</div>' +
      '<div class="ref">Proverbs ' + day + '<span>Chapter ' + day + '</span></div>' +
      '<div class="ref">' + psLabel + '<span>' + (ps.end - ps.start + 1) + ' chapter' + (ps.end - ps.start > 0 ? 's' : '') + '</span></div>' +
      '<button class="check-btn' + (isDone ? ' checked' : '') + '" onclick="toggle(' + day + ',' + m + ',' + y + ')" title="Mark done">' +
      '<svg class="check-icon" viewBox="0 0 16 16"><polyline points="3,8 6,12 13,4"/></svg>' +
      '</button>';
    row.addEventListener('click', (ev) => {
      if (ev.target.closest('.check-btn')) return;
      openNote(day, m, y);
    });
    grid.appendChild(row);
  }

  updateStats(days);
  // Auto-scroll to today only when it's off-screen
  if (parseInt(document.getElementById('monthSel').value) === now.getMonth() && parseInt(document.getElementById('yearSel').value) === now.getFullYear()) {
    const auto = document.getElementById('autoScroll') && document.getElementById('autoScroll').checked;
    if (auto) {
      const todayEl = grid.querySelector('.day-row.today');
      if (todayEl) {
        const rect = todayEl.getBoundingClientRect();
        if (rect.top < 0 || rect.bottom > window.innerHeight) {
          todayEl.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }
      }
    }
  }
}

function toggle(day, m, y) {
  const entry = monthData[day] || { done: false, note: '' };
  entry.done = !entry.done;
  monthData[day] = entry;
  // cleanup empty entries
  if (!entry.done && !entry.note) delete monthData[day];
  saveMonthData(m, y, monthData);
  render();
}

function resetMonth() {
  const m = parseInt(document.getElementById('monthSel').value);
  const y = parseInt(document.getElementById('yearSel').value);
  monthData = {};
  saveMonthData(m, y, {});
  render();
}

function updateStats(days) {
  const done = Object.values(monthData).filter(v => v && v.done).length;
  const left = days - done;
  const pct = Math.round((done / days) * 100) || 0;
  document.getElementById('sDone').textContent = done;
  document.getElementById('sLeft').textContent = left;
  document.getElementById('sPct').textContent = pct + '%';
  document.getElementById('pBar').style.width = pct + '%';
}

function openNote(day, m, y) {
  selected = { day, m, y };
  const panel = document.getElementById('notePanel');
  document.getElementById('noteDate').textContent = MONTHS[m] + ' ' + day + ', ' + y;
  document.getElementById('noteText').value = (monthData[day] && monthData[day].note) || '';
  panel.style.display = 'block';
}

function closeNote() { document.getElementById('notePanel').style.display = 'none'; selected = null; }

function saveNote() {
  if (!selected) return;
  const text = document.getElementById('noteText').value.trim();
  const entry = monthData[selected.day] || { done: false, note: '' };
  entry.note = text;
  monthData[selected.day] = entry;
  // remove if empty
  if (!entry.done && !entry.note) delete monthData[selected.day];
  saveMonthData(selected.m, selected.y, monthData);
  render();
  closeNote();
}

function deleteNote() {
  if (!selected) return;
  const entry = monthData[selected.day];
  if (entry) {
    entry.note = '';
    if (!entry.done) delete monthData[selected.day];
    else monthData[selected.day] = entry;
    saveMonthData(selected.m, selected.y, monthData);
  }
  render();
  closeNote();
}

function exportMonth() {
  const m = parseInt(document.getElementById('monthSel').value);
  const y = parseInt(document.getElementById('yearSel').value);
  const data = { meta: { month: m, year: y, exportedAt: new Date().toISOString() }, data: getMonthData(m, y) };
  const blob = new Blob([JSON.stringify(data, null, 2)], { type: 'application/json' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = `bplan_${y}_${m}.json`;
  document.body.appendChild(a);
  a.click();
  a.remove();
  URL.revokeObjectURL(url);
}

function importMonth(ev) {
  const file = ev.target.files && ev.target.files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = function(e) {
    try {
      const parsed = JSON.parse(e.target.result);
      const m = parseInt(document.getElementById('monthSel').value);
      const y = parseInt(document.getElementById('yearSel').value);
      // Support both {meta,data} exports or direct map
      const payload = parsed.data || parsed;
      saveMonthData(m, y, payload);
      render();
      alert('Imported to current month.');
    } catch (err) { alert('Invalid JSON file'); }
  };
  reader.readAsText(file);
  // clear input
  ev.target.value = '';
}

render();
</script>
</body>
</html>
