<!-- README.es.md -->

🌍 English version: [README.md](README.md)

<div align="center" role="banner" aria-label="Encabezado del proyecto">

<h1>Conventional Commits — guía práctica y plantilla reproducible (2026)</h1>

<p><strong>Practical guide + templates de Conventional Commits para equipos y proyectos reales</strong><br/>
Guía clara, aplicable y sin fricción para usar Conventional Commits con mapeo a SemVer.</p>

<p><sub>Research actualizado: 02/2026 · Basado en la especificación Conventional Commits v1.0.0</sub></p>

<br/>

<nav aria-label="Navegación rápida">
<a href="#por-qué-esta-guía-existe">Por qué</a> ·
<a href="#regla-base-en-20-segundos">Regla base</a> ·
<a href="#cheat-sheet-de-tipos">Cheat sheet</a> ·
<a href="#cómo-escribir-buenas-descripciones-de-commit">Descripciones</a> ·
<a href="#plantillas-reutilizables">Plantillas</a> ·
<a href="#semver-sin-misterio">SemVer</a> ·
<a href="#uso-en-equipos">Equipos</a>
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

<section id="por-qué-esta-guía-existe" aria-labelledby="por-que-heading">

<h2 id="por-que-heading">Por qué esta guía existe</h2>

<p>
  Soy <strong>Data Analyst Junior</strong> y estoy formándome en mi bootcamp con Factoría F5.<br/>
  Trabajando en proyectos académicos y técnicos vi un patrón: el problema no suele ser el código… es la <strong>historia de cambios mal contada</strong>.
</p>

<div align="center" role="region" aria-label="Problemas causados por commits poco claros">
  <table role="table" aria-describedby="tabla-problemas">
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
        <td><strong>Commits confusos</strong></td>
        <td><strong>Revisiones lentas</strong></td>
        <td><strong>Bugs difíciles de rastrear</strong></td>
        <td><strong>Releases con miedo</strong></td>
      </tr>
    </tbody>
  </table>
</div>

<p>
  Así que hice un research actualizado sobre <strong>Conventional Commits</strong> y lo trabajé usando uno de los métodos de aprendizaje que aplicamos en el bootcamp:
  explicar lo complejo en simple para comprobar que realmente está entendido.
</p>

<p>
  Lo desarrollé aplicando el método Feynman (<em>aprender → explicar → simplificar → reutilizar</em>) para convertir el conocimiento en práctica clara.
  Y convertí ese proceso en una guía práctica y reutilizable. No solo para estudiarlo, sino para poder aplicarlo en proyectos reales y compartirlo con equipos.
</p>

<blockquote>
  <p>Si cualquiera puede entender tus commits en segundos, tu proyecto escala mejor.</p>
</blockquote>

<p><em>Documentar bien es también una forma de pensar mejor.</em></p>

<p>Este README está pensado para:</p>

<ul>
<li>personas que trabajan con Git en proyectos reales</li>
<li>estudiantes y perfiles junior que quieren una convención clara</li>
<li>equipos que quieren reducir fricción en revisiones y releases</li>
<li>repositorios que buscan commits consistentes y automatizables</li>
</ul>

</section>

<hr/>

<section aria-labelledby="que-es-heading">

<h2 id="que-es-heading">Qué es Conventional Commits</h2>

<p>Conventional Commits es una convención para escribir mensajes de commit con estructura clara.</p>

<p>Permite:</p>

<ul>
<li>changelogs automáticos</li>
<li>versionado SemVer consistente</li>
<li>clasificación de cambios</li>
<li>automatización de releases</li>
<li>mejor revisión de PRs</li>
<li>menos fricción en equipo</li>
</ul>

</section>

<hr/>

<section id="regla-base-en-20-segundos" aria-labelledby="regla-heading">

<h2 id="regla-heading">Regla base en 20 segundos</h2>

<p><strong>Formato:</strong></p>

<pre><code>type(scope)!: mensaje claro en imperativo
</code></pre>

<p><strong>Significa:</strong></p>

<ul>
<li><strong>type</strong> → tipo de cambio (feat, fix, docs…)</li>
<li><strong>scope</strong> → zona afectada (opcional)</li>
<li><strong>!</strong> → breaking change</li>
<li><strong>mensaje</strong> → qué cambia y para qué</li>
</ul>

<p><strong>Ejemplo:</strong></p>

<pre><code>feat(etl): add incremental load for customers
</code></pre>

<div align="center" role="figure" aria-label="Anatomía de un commit convencional">

<p><strong>Anatomía de un commit</strong></p>

<img src="assets/visual-guides/anatomia-conventional-commit.png"
     width="720"
     alt="Anatomia de un Conventional Commit">

<p><sub>Desglose visual de cada parte del mensaje de commit.</sub></p>

</div>

</section>

<hr/>

<section id="cheat-sheet-de-tipos" aria-labelledby="types-heading">

<h2 id="types-heading">Cheat sheet de tipos</h2>

<p>Set más compatible con tooling y equipos.</p>

<table role="table" aria-label="Cheat sheet de tipos de commit">
<thead>
<tr>
<th scope="col">type</th>
<th scope="col">Cuándo usarlo</th>
<th scope="col">Ejemplo</th>
</tr>
</thead>
<tbody>

<tr><th scope="row"><code>feat</code></th><td>Nueva funcionalidad</td><td><code>feat(api): add export endpoint</code></td></tr>
<tr><th scope="row"><code>fix</code></th><td>Corrección de bug</td><td><code>fix(ui): prevent modal overflow</code></td></tr>
<tr><th scope="row"><code>perf</code></th><td>Mejora de rendimiento</td><td><code>perf(sql): optimize join strategy</code></td></tr>
<tr><th scope="row"><code>refactor</code></th><td>Cambio interno sin alterar comportamiento</td><td><code>refactor(model): split pipeline</code></td></tr>
<tr><th scope="row"><code>docs</code></th><td>Documentación</td><td><code>docs: add data dictionary</code></td></tr>
<tr><th scope="row"><code>test</code></th><td>Tests</td><td><code>test(api): add edge cases</code></td></tr>
<tr><th scope="row"><code>style</code></th><td>Formato / lint</td><td><code>style: apply formatter</code></td></tr>
<tr><th scope="row"><code>build</code></th><td>Dependencias / build</td><td><code>build: bump numpy</code></td></tr>
<tr><th scope="row"><code>ci</code></th><td>CI/CD</td><td><code>ci: add pipeline cache</code></td></tr>
<tr><th scope="row"><code>chore</code></th><td>Mantenimiento general</td><td><code>chore: update gitignore</code></td></tr>
<tr><th scope="row"><code>revert</code></th><td>Reversión</td><td><code>revert: feat(api): export endpoint</code></td></tr>

</tbody>
</table>

<div align="center" role="figure" aria-label="Árbol de decisión para elegir tipo de commit">

<p><strong>Cómo elegir el tipo de commit</strong></p>

<img src="assets/visual-guides/arbol-decision-tipo-commit.png"
     width="720"
     alt="Arbol de decision tipo commit">

<p><sub>Ruta rápida para elegir el type correcto sin dudas.</sub></p>

</div>

</section>

<hr/>

<section id="cómo-escribir-buenas-descripciones-de-commit" aria-labelledby="desc-heading">

<h2 id="desc-heading">Cómo escribir buenas descripciones de commits</h2>

<p>Un buen commit debería entenderse sin abrir el diff.</p>

<blockquote>
<p>diff = vista de diferencias línea a línea que muestra qué código cambió exactamente.</p>
</blockquote>

<p>Sirve para:</p>

<ul>
<li>tu yo futuro</li>
<li>quien revisa tu PR</li>
<li>quien entra nuevo al proyecto</li>
<li>herramientas de changelog</li>
</ul>

<blockquote>
<p>Regla clave: <strong>qué cambia + para qué cambia</strong></p>
</blockquote>

<p>No describas el archivo. Describe el resultado.</p>

<h3>Método práctico</h3>

<p>Piensa primero en español → escribe luego en inglés si tu repo lo usa.</p>

<p><strong>Fórmula:</strong></p>

<pre><code>verbo + objeto + contexto mínimo
</code></pre>

<p>Ejemplo mental:<br/>
“evitar duplicados en reintentos del ETL”</p>

<p>Commit final:</p>

<pre><code>fix(etl): prevent duplicate rows on retry
</code></pre>

<h3>Verbos útiles (rápida referencia)</h3>

<p>add · fix · prevent · improve · reduce · support · validate · simplify · split · remove</p>

<p>Evita verbos vagos:</p>

<p>update · change · tweaks · stuff · misc</p>

<div align="center" role="figure" aria-label="Verbos fuertes para commits">

<p><strong>✍️ Verbos fuertes para mensajes de commit</strong></p>

<img src="assets/visual-guides/verbos-mensajes-commit-cheatsheet.png"
     width="720"
     alt="Verbos para mensajes de commit">

<p><sub>Verbos claros hacen commits claros.</sub></p>

</div>

<h3>Ejemplos de commits claros</h3>

<pre><code>fix(api): handle null user_id in payload
feat(model): add churn probability feature
perf(sql): reduce join cost in revenue report
docs: add data dictionary for sales table
</code></pre>

<h3>Test rápido de calidad (10 segundos)</h3>

<p>Si sí → commit sólido.</p>

<div align="center" role="figure" aria-label="Checklist de calidad de commit">

<p><strong>Checklist de calidad del commit</strong></p>

<img src="assets/visual-guides/checklist-calidad-commit.png"
     width="720"
     alt="Checklist calidad commit">

<p><sub>Auto-revisión rápida antes de hacer push.</sub></p>

</div>

<h3>Regla de oro para equipos</h3>

<p>Mejor un commit <strong>simple y claro</strong> que perfecto pero ambiguo.<br/>
La consistencia del equipo vale más que la creatividad individual.</p>

</section>

<hr/>

<section id="plantillas-reutilizables" aria-labelledby="templates-heading">

<h2 id="templates-heading">Plantillas reutilizables</h2>

<h3>Commit simple</h3>

<pre><code>type(scope): verbo + objeto + contexto
</code></pre>

<h3>Commit con contexto</h3>

<pre><code>type(scope): cambio principal

Motivo: por qué era necesario
Impacto: qué mejora o evita
</code></pre>

</section>

<hr/>

<section aria-labelledby="breaking-heading">

<h2 id="breaking-heading">Breaking changes (muy importante!!)</h2>

<p>Si rompe compatibilidad:</p>

<pre><code>feat(api)!: rename customer_id to client_id

BREAKING CHANGE: field renamed in all responses
</code></pre>

<p>Eso permite a las herramientas marcar versión mayor automáticamente.</p>

</section>

<hr/>

<section id="semver-sin-misterio" aria-labelledby="semver-heading">

<h2 id="semver-heading">SemVer, sin complicarnos (prometido)</h2>

<p>Si tus commits están bien escritos, SemVer casi se calcula solo.<br/>
La magia de la consistencia.</p>

<p>Mapping típico:</p>

<ul>
<li>MAJOR → <code>!</code> o BREAKING CHANGE</li>
<li>MINOR → feat</li>
<li>PATCH → fix / perf</li>
<li>sin release → docs, test, style, chore, ci…</li>
</ul>

<p>Configurable por equipo.</p>

</section>

<hr/>

<section id="uso-en-equipos" aria-labelledby="equipos-heading">

<h2 id="equipos-heading">Uso en equipos (reglas que evitan discusiones)</h2>

<p>En 2026 el problema rara vez es “cómo escribir un commit”.<br/>
El problema es el día a día: cambios que llegan rápido (y a veces con AI), contexto que se pierde, documentación que se queda atrás y tiempo que se va en preguntar lo mismo por tercera vez.</p>

<p>Cuando faltan señales claras, los equipos pagan el “impuesto de coordinación”: más revisiones, más onboarding lento, más dudas al release.<br/>
La buena noticia: una convención pequeña (y constante) reduce muchísimo esa fricción.</p>

<ul>
<li>No inventar <code>types</code> sin documentarlos (si no está en la guía del repo, no existe)</li>
<li>Elegir idioma y mantenerlo (se recomienda inglés en commits por compatibilidad con tooling y equipos internacionales)</li>
<li>Un commit = una intención (si estás contando dos historias, separa en dos commits)</li>
<li>Si dudas, describe el impacto (qué cambia + para qué cambia)</li>
<li>Consistencia &gt; perfección (la claridad del equipo gana a la brillantez individual)</li>
<li>Si usas asistentes, revisa el mensaje como si fueras la persona que hará el onboarding (claridad primero)</li>
</ul>

</section>

<hr/>

<section aria-labelledby="uso-guia-heading">

<h2 id="uso-guia-heading">Cómo usar esta guía en la práctica</h2>

<p>Esta guía está diseñada para uso directo:</p>

<ul>
<li>como referencia rápida mientras haces commits</li>
<li>como plantilla base de CONTRIBUTING.md</li>
<li>como estándar de equipo</li>
<li>como material de onboarding técnico</li>
<li>como recurso didáctico en clases y bootcamps</li>
</ul>

<p>Puedes copiar, adaptar y reutilizar las plantillas según tu flujo de trabajo.</p>

</section>

<hr/>

<section aria-labelledby="refs-heading">

<h2 id="refs-heading">Referencias</h2>

<ul>
<li>https://www.conventionalcommits.org/en/v1.0.0/</li>
<li>https://github.com/conventional-changelog/commitlint</li>
<li>https://github.com/semantic-release/commit-analyzer</li>
</ul>

</section>

<hr/>

<footer align="center" role="contentinfo">

<h2>Si esta guía te ahorra tiempo en tu día a día técnico, hazla circular</h2>

<p><sub>Dale ⭐, compártela o pásasela a la próxima persona que entre a tu equipo.</sub></p>

</footer>

</main>
