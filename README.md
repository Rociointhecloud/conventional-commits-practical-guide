<!-- README.md -->

🌍 Spanish version: [README.es.md](README.es.md)

<div align="center" role="banner" aria-label="Project header">

<h1>Conventional Commits — practical guide and reproducible template (2026)</h1>

<p><strong>Practical guide + Conventional Commits templates for real teams and real projects</strong><br/>
Clear, frictionless guidance for using Conventional Commits with SemVer mapping.</p>

<p><sub>Updated research: 02/2026 · Based on the Conventional Commits v1.0.0 specification</sub></p>

<br/>

<nav aria-label="Quick navigation">
<a href="#why-this-guide-exists">Why</a> ·
<a href="#the-20-second-rule">Base rule</a> ·
<a href="#commit-type-cheat-sheet">Cheat sheet</a> ·
<a href="#how-to-write-good-commit-descriptions">Descriptions</a> ·
<a href="#reusable-templates">Templates</a> ·
<a href="#semver-without-the-mystery">SemVer</a> ·
<a href="#team-usage">Teams</a>
</nav>

<br/><br/>

<p>
<img alt="Conventional Commits" src="https://img.shields.io/badge/Conventional%20Commits-v1.0.0-orange" />
<img alt="SemVer" src="https://img.shields.io/badge/SemVer-ready-brightgreen" />
<img alt="Guide" src="https://img.shields.io/badge/Practical%20Guide-Templates-blue" />
</p>

</div>

<hr/>

<main role="main">

<section id="why-this-guide-exists" aria-labelledby="why-heading">

<h2 id="why-heading">Why this guide exists</h2>

<p>
  I’m a <strong>Junior Data Analyst</strong> and I’m training in my bootcamp with Factoría F5.<br/>
  Working on academic and technical projects, I noticed a pattern: the problem usually isn’t the code… it’s the <strong>change history being told poorly</strong>.
</p>

<div align="center" role="region" aria-label="Problems caused by unclear commits">
  <table role="table" aria-describedby="problems-table">
    <thead>
      <tr>
        <th scope="col">❓</th>
        <th scope="col">🐢</th>
        <th scope="col">🧩</th>
        <th scope="col">😬</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Confusing commits</strong></td>
        <td><strong>Slow reviews</strong></td>
        <td><strong>Hard-to-trace bugs</strong></td>
        <td><strong>Scary releases</strong></td>
      </tr>
    </tbody>
  </table>
</div>

<p>
  So I did updated research on <strong>Conventional Commits</strong> and worked through it using one of the learning methods we apply in the bootcamp:
  explaining complex things simply to verify they’re truly understood.
</p>

<p>
  I developed it by applying the Feynman method (<em>learn → explain → simplify → reuse</em>) to turn knowledge into clear practice.
  And I turned that process into a practical, reusable guide. Not just to study it, but to apply it in real projects and share it with teams.
</p>

<blockquote>
  <p>If anyone can understand your commits in seconds, your project scales better.</p>
</blockquote>

<p><em>Good documentation is also a way to think better.</em></p>

<p>This README is intended for:</p>

<ul>
<li>people using Git in real projects</li>
<li>students and junior profiles who want a clear convention</li>
<li>teams that want to reduce friction in reviews and releases</li>
<li>repositories that want consistent, automatable commits</li>
</ul>

</section>

<hr/>

<section aria-labelledby="what-is-heading">

<h2 id="what-is-heading">What is Conventional Commits</h2>

<p>Conventional Commits is a convention for writing commit messages with a clear structure.</p>

<p>It enables:</p>

<ul>
<li>automatic changelogs</li>
<li>consistent SemVer versioning</li>
<li>change classification</li>
<li>release automation</li>
<li>better PR reviews</li>
<li>less team friction</li>
</ul>

</section>

<hr/>

<section id="the-20-second-rule" aria-labelledby="rule-heading">

<h2 id="rule-heading">The 20-second rule</h2>

<p><strong>Format:</strong></p>

<pre><code>type(scope)!: clear imperative message
</code></pre>

<p><strong>Meaning:</strong></p>

<ul>
<li><strong>type</strong> → kind of change (feat, fix, docs…)</li>
<li><strong>scope</strong> → affected area (optional)</li>
<li><strong>!</strong> → breaking change</li>
<li><strong>message</strong> → what changes and why</li>
</ul>

<p><strong>Example:</strong></p>

<pre><code>feat(etl): add incremental load for customers
</code></pre>

<div align="center" role="figure" aria-label="Conventional commit anatomy">

<p><strong>Commit anatomy</strong></p>

<img src="assets/visual-guides/conventional-commit-anatomy-en.png"
     width="720"
     alt="Conventional Commit anatomy">

<p><sub>Visual breakdown of each part of a commit message.</sub></p>

</div>

</section>

<hr/>

<section id="commit-type-cheat-sheet" aria-labelledby="types-heading">

<h2 id="types-heading">Commit type cheat sheet</h2>

<p>The most compatible set for tooling and teams.</p>

<table role="table" aria-label="Commit type cheat sheet">
<thead>
<tr>
<th scope="col">type</th>
<th scope="col">When to use it</th>
<th scope="col">Example</th>
</tr>
</thead>
<tbody>

<tr><th scope="row"><code>feat</code></th><td>New functionality</td><td><code>feat(api): add export endpoint</code></td></tr>
<tr><th scope="row"><code>fix</code></th><td>Bug fix</td><td><code>fix(ui): prevent modal overflow</code></td></tr>
<tr><th scope="row"><code>perf</code></th><td>Performance improvement</td><td><code>perf(sql): optimize join strategy</code></td></tr>
<tr><th scope="row"><code>refactor</code></th><td>Internal change without behavior changes</td><td><code>refactor(model): split pipeline</code></td></tr>
<tr><th scope="row"><code>docs</code></th><td>Documentation</td><td><code>docs: add data dictionary</code></td></tr>
<tr><th scope="row"><code>test</code></th><td>Tests</td><td><code>test(api): add edge cases</code></td></tr>
<tr><th scope="row"><code>style</code></th><td>Formatting / lint</td><td><code>style: apply formatter</code></td></tr>
<tr><th scope="row"><code>build</code></th><td>Dependencies / build</td><td><code>build: bump numpy</code></td></tr>
<tr><th scope="row"><code>ci</code></th><td>CI/CD</td><td><code>ci: add pipeline cache</code></td></tr>
<tr><th scope="row"><code>chore</code></th><td>General maintenance</td><td><code>chore: update gitignore</code></td></tr>
<tr><th scope="row"><code>revert</code></th><td>Reversion</td><td><code>revert: feat(api): export endpoint</code></td></tr>

</tbody>
</table>

<div align="center" role="figure" aria-label="Decision tree for choosing a commit type">

<p><strong>How to choose the right commit type</strong></p>

<img src="assets/visual-guides/commit-type-decision-tree-en.png"
     width="720"
     alt="Decision tree for commit type selection">

<p><sub>Fast path to choosing the right type with no doubts.</sub></p>

</div>

</section>

<hr/>

<section id="how-to-write-good-commit-descriptions" aria-labelledby="desc-heading">

<h2 id="desc-heading">How to write good commit descriptions</h2>

<p>A good commit should be understandable without opening the diff.</p>

<blockquote>
<p>diff = a line-by-line view of changes showing exactly what code changed.</p>
</blockquote>

<p>It’s for:</p>

<ul>
<li>future you</li>
<li>whoever reviews your PR</li>
<li>anyone new joining the project</li>
<li>changelog tooling</li>
</ul>

<blockquote>
<p>Key rule: <strong>what changes + why it changes</strong></p>
</blockquote>

<p>Don’t describe the file. Describe the outcome.</p>

<h3>Practical method</h3>

<p>Think in your clearest language first → then write in English if that’s what your repo uses.</p>

<p><strong>Formula:</strong></p>

<pre><code>verb + object + minimal context
</code></pre>

<p>Mental example:<br/>
“avoid duplicates on ETL retries”</p>

<p>Final commit:</p>

<pre><code>fix(etl): prevent duplicate rows on retry
</code></pre>

<h3>Useful verbs (quick reference)</h3>

<p>add · fix · prevent · improve · reduce · support · validate · simplify · split · remove</p>

<p>Avoid vague verbs:</p>

<p>update · change · tweaks · stuff · misc</p>

<div align="center" role="figure" aria-label="Strong verbs for commit messages">

<p><strong>✍️ Strong verbs for commit messages</strong></p>

<img src="assets/visual-guides/commit-message-verbs-cheatsheet-en.png"
     width="720"
     alt="Strong verbs for commit messages">

<p><sub>Clear verbs make clear commits.</sub></p>

</div>

<h3>Examples of clear commits</h3>

<pre><code>fix(api): handle null user_id in payload
feat(model): add churn probability feature
perf(sql): reduce join cost in revenue report
docs: add data dictionary for sales table
</code></pre>

<h3>Quick quality test (10 seconds)</h3>

<p>If yes → solid commit.</p>

<div align="center" role="figure" aria-label="Commit quality checklist">

<p><strong>Commit quality checklist</strong></p>

<img src="assets/visual-guides/commit-quality-checklist-en.png"
     width="720"
     alt="Commit quality checklist">

<p><sub>Fast self-review before pushing.</sub></p>

</div>

<h3>Golden rule for teams</h3>

<p>Better a <strong>simple and clear</strong> commit than a perfect but ambiguous one.<br/>
Team consistency matters more than individual creativity.</p>

</section>

<hr/>

<section id="reusable-templates" aria-labelledby="templates-heading">

<h2 id="templates-heading">Reusable templates</h2>

<h3>Simple commit</h3>

<pre><code>type(scope): verb + object + context
</code></pre>

<h3>Commit with context</h3>

<pre><code>type(scope): main change

Reason: why it was necessary
Impact: what it improves or prevents
</code></pre>

</section>

<hr/>

<section aria-labelledby="breaking-heading">

<h2 id="breaking-heading">Breaking changes (very important!!)</h2>

<p>If it breaks compatibility:</p>

<pre><code>feat(api)!: rename customer_id to client_id

BREAKING CHANGE: field renamed in all responses
</code></pre>

<p>This allows tools to automatically bump the major version.</p>

</section>

<hr/>

<section id="semver-without-the-mystery" aria-labelledby="semver-heading">

<h2 id="semver-heading">SemVer, without the mystery (promise)</h2>

<p>If your commits are well written, SemVer almost calculates itself.<br/>
The magic of consistency.</p>

<p>Typical mapping:</p>

<ul>
<li>MAJOR → <code>!</code> or BREAKING CHANGE</li>
<li>MINOR → feat</li>
<li>PATCH → fix / perf</li>
<li>no release → docs, test, style, chore, ci…</li>
</ul>

<p>Configurable per team.</p>

</section>

<hr/>

<section id="team-usage" aria-labelledby="teams-heading">

<h2 id="teams-heading">Team usage (rules that prevent debates)</h2>

<p>In 2026, the problem is rarely “how to write a commit”.<br/>
The problem is the day-to-day: changes arriving fast (and sometimes with AI), context getting lost, documentation falling behind, and time spent answering the same question for the third time.</p>

<p>When clear signals are missing, teams pay the “coordination tax”: more review cycles, slower onboarding, more uncertainty at release time.<br/>
The good news: a small (and consistent) convention reduces that friction significantly.</p>

<ul>
<li>Don’t invent <code>types</code> without documenting them (if it’s not in the repo’s guide, it doesn’t exist)</li>
<li>Pick a language and stick to it (English is recommended for commits due to tooling compatibility and international teams)</li>
<li>One commit = one intent (if you’re telling two stories, split into two commits)</li>
<li>If in doubt, describe the impact (what changes + why it changes)</li>
<li>Consistency &gt; perfection (team clarity beats individual brilliance)</li>
<li>If you use assistants, review the message as if you were the person doing onboarding (clarity first)</li>
</ul>

</section>

<hr/>

<section aria-labelledby="how-to-use-heading">

<h2 id="how-to-use-heading">How to use this guide in practice</h2>

<p>This guide is designed for direct use:</p>

<ul>
<li>as a quick reference while committing</li>
<li>as a base template for CONTRIBUTING.md</li>
<li>as a team standard</li>
<li>as technical onboarding material</li>
<li>as a teaching resource in classes and bootcamps</li>
</ul>

<p>You can copy, adapt, and reuse the templates depending on your workflow.</p>

</section>

<hr/>

<section aria-labelledby="refs-heading">

<h2 id="refs-heading">References</h2>

<ul>
<li>https://www.conventionalcommits.org/en/v1.0.0/</li>
<li>https://github.com/conventional-changelog/commitlint</li>
<li>https://github.com/semantic-release/commit-analyzer</li>
</ul>

</section>

<hr/>

<footer align="center" role="contentinfo">

<h2>If this guide saves you time in your day-to-day technical work, pass it on</h2>

<p><sub>Give it a ⭐, share it, or send it to the next person who joins your team.</sub></p>

</footer>

</main>
