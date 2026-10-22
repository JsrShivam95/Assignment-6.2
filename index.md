HTML

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 6.2 — Backgrounds, Borders &amp; Display</title>
  <meta name="description" content="Three distinct tier cards showcasing CSS backgrounds, borders, radii, and display properties.">
  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>💳</text></svg>">
  <link rel="stylesheet" href="cards.css">
</head>
<body>

  <header class="page-header">
    <h1>Membership &amp; Service Tiers</h1>
    <p>Comparing visual styling, borders, backgrounds, and CSS <code>display</code> behaviors.</p>
  </header>

  <main class="cards-wrapper">

    <!-- Card 1: Basic Tier -->
    <article class="card card-basic">
      <div class="card-content">
        <!-- display: inline demonstration -->
        <span class="plan-tag">Free Tier</span>
        <h2 class="card-title">Basic Plan</h2>
        <div class="price-box">
          <span class="currency">$</span><span class="amount">0</span><span class="period">/mo</span>
        </div>
        <p class="card-description">
          Essential tools for individuals starting out. Includes community forum support and standard single-project exports.
        </p>
      </div>
      <!-- display: inline-block demonstration -->
      <a href="#basic" class="btn btn-basic">Get Started</a>
    </article>

    <!-- Card 2: Standard Tier (Popular / Elevated) -->
    <article class="card card-standard">
      <div class="card-badge">Most Popular</div>
      <div class="card-content">
        <span class="plan-tag">Growth Tier</span>
        <h2 class="card-title">Standard Plan</h2>
        <div class="price-box">
          <span class="currency">$</span><span class="amount">29</span><span class="period">/mo</span>
        </div>
        <p class="card-description">
          Ideal for growing teams needing automated workflows, unlimited projects, priority email ticketing, and cloud backups.
        </p>
      </div>
      <a href="#standard" class="btn btn-standard">Choose Standard</a>
    </article>

    <!-- Card 3: Premium Tier (Luxury Gradient) -->
    <article class="card card-premium">
      <div class="card-content">
        <span class="plan-tag">Enterprise Tier</span>
        <h2 class="card-title">Premium Plan</h2>
        <div class="price-box">
          <span class="currency">$</span><span class="amount">79</span><span class="period">/mo</span>
        </div>
        <p class="card-description">
          Enterprise-level power with dedicated account managers, 99.9% SLA guarantees, customized security, and 24/7 phone access.
        </p>
      </div>
      <a href="#premium" class="btn btn-premium">Go Premium</a>
    </article>

  </main>

  <footer class="page-footer">
    <p>&copy; 2026 Display &amp; Borders Lab. All rights reserved.</p>
  </footer>

</body>
</html>

CSS

/* ==========================================================================
   Base Reset & Layout Setup
   ========================================================================== */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  background-color: #f1f5f9;
  color: #334155;
  line-height: 1.6;
  padding: 40px 16px;
}

/* Step 5: display: block demonstration */
/* The header, title, and paragraphs occupy full container width on their own lines */
.page-header {
  display: block;
  text-align: center;
  margin-bottom: 40px;
}

.page-header h1 {
  display: block;
  font-size: 2.25rem;
  color: #0f172a;
  margin-bottom: 8px;
}

.page-header p {
  display: block;
  font-size: 1rem;
  color: #64748b;
}

/* ==========================================================================
   Step 6: Dimensions (width, min/max-height, max-width)
   ========================================================================== */
.cards-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: stretch;
  gap: 24px;
  width: 100%;
  max-width: 1100px; /* Constrains total layout width on wide monitors */
  margin: 0 auto;
}

.card {
  /* Enforcing responsive constraints per card */
  width: 100%;
  max-width: 330px;  /* Step 6: Maximum width per card */
  min-height: 440px;  /* Step 6: Controlled height ensuring card alignment */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 32px 24px;
  position: relative;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.card:hover {
  transform: translateY(-6px);
}

/* ==========================================================================
   Step 5: Practical Demonstrations of display Properties
   ========================================================================== */

/* 1. display: inline */
/* Sits directly within text flow; ignores vertical margin & height */
.currency,
.period {
  display: inline;
  font-size: 1rem;
  color: #64748b;
}

/* 2. display: inline-block */
/* Flows inline like text, but honors explicit padding, widths, and border-radius */
.plan-tag {
  display: inline-block;
  padding: 4px 12px;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  border-radius: 999px; /* Pill shape */
  margin-bottom: 12px;
}

/* Buttons use display: inline-block so they accept width/height/padding while being anchor tags */
.btn {
  display: inline-block;
  width: 100%;
  text-align: center;
  padding: 12px 20px;
  font-size: 0.95rem;
  font-weight: 600;
  text-decoration: none;
  cursor: pointer;
  transition: background-color 0.2s ease, border-color 0.2s ease;
}

/* 3. display: block */
.card-title {
  display: block;
  font-size: 1.5rem;
  margin-bottom: 12px;
  color: #0f172a;
}

.card-description {
  display: block;
  font-size: 0.92rem;
  color: #64748b;
  margin-top: 14px;
}

.price-box {
  display: block;
  margin: 12px 0;
}

.amount {
  display: inline;
  font-size: 2.5rem;
  font-weight: 800;
  color: #0f172a;
}

/* ==========================================================================
   Step 3 & 4: Distinct Backgrounds, Borders, and border-radius
   ========================================================================== */

/* Card 1: Basic Plan (Clean outline, solid white background, subtle border) */
.card-basic {
  background-color: #ffffff;
  border: 1px solid #cbd5e1;
  border-radius: 8px; /* Step 4: Rounded corners */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.04);
}

.card-basic .plan-tag {
  background-color: #f1f5f9;
  color: #475569;
}

.btn-basic {
  background-color: transparent;
  color: #0f172a;
  border: 2px solid #cbd5e1;
  border-radius: 6px;
}

.btn-basic:hover {
  background-color: #f8fafc;
  border-color: #94a3b8;
}

/* Card 2: Standard Plan (Vibrant blue accent border, tinted background) */
.card-standard {
  background-color: #ffffff;
  border: 2px solid #2563eb;
  border-radius: 16px; /* Step 4: Distinct radius */
  box-shadow: 0 10px 25px rgba(37, 99, 235, 0.12);
}

.card-standard .plan-tag {
  background-color: #eff6ff;
  color: #2563eb;
}

.card-badge {
  position: absolute;
  top: -14px;
  left: 50%;
  transform: translateX(-50%);
  background-color: #2563eb;
  color: #ffffff;
  font-size: 0.75rem;
  font-weight: 700;
  padding: 4px 14px;
  border-radius: 999px;
  text-transform: uppercase;
}

.btn-standard {
  background-color: #2563eb;
  color: #ffffff;
  border: 2px solid #2563eb;
  border-radius: 8px;
}

.btn-standard:hover {
  background-color: #1d4ed8;
  border-color: #1d4ed8;
}

/* Card 3: Premium Plan (Rich dark gradient, gold/amber accent border) */
.card-premium {
  background: linear-gradient(145deg, #0f172a 0%, #1e293b 100%);
  border: 2px solid #f59e0b; /* Amber/gold border */
  border-radius: 24px;       /* Step 4: Maximum corner curve */
  box-shadow: 0 12px 28px rgba(15, 23, 42, 0.25);
  color: #f8fafc;
}

.card-premium .card-title,
.card-premium .amount {
  color: #ffffff;
}

.card-premium .card-description,
.card-premium .currency,
.card-premium .period {
  color: #94a3b8;
}

.card-premium .plan-tag {
  background-color: rgba(245, 158, 11, 0.15);
  color: #fbbf24;
  border: 1px solid rgba(245, 158, 11, 0.3);
}

.btn-premium {
  background: linear-gradient(135deg, #f59e0b 0%, #d97706 100%);
  color: #0f172a;
  font-weight: 700;
  border: 2px solid #f59e0b;
  border-radius: 12px;
}

.btn-premium:hover {
  background: linear-gradient(135deg, #d97706 0%, #b45309 100%);
  border-color: #d97706;
  color: #ffffff;
}

/* Footer */
.page-footer {
  text-align: center;
  margin-top: 48px;
  font-size: 0.85rem;
  color: #94a3b8;
}