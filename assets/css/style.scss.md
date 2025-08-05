---
---
@import "minima";

/* ✅ Typography */
body {
  font-family: 'Helvetica Neue', sans-serif;
  background-color: #FAFAF7;
  color: #2D6B2B;
}

/* ✅ Link colors */
a {
  color: #2D6B2B;
}

a:hover {
  color: #7DB659;
  text-decoration: underline;
}

/* ✅ Header + Footer */
.site-header,
.site-footer {
  background-color: #F0F0ED;
  border-top: 4px solid #2D6B2B;
}

.site-title, .site-nav a {
  color: #2D6B2B !important;
}

/* ✅ Page content layout */
.page-content {
  max-width: 750px;
  margin: 0 auto;
  padding: 2rem 1rem;
}

/* ✅ Button / highlight elements (optional) */
button, .button {
  background-color: #2D6B2B;
  color: white;
  border-radius: 4px;
  padding: 0.4em 1em;
  border: none;
  font-weight: bold;
}

button:hover, .button:hover {
  background-color: #7DB659;
  cursor: pointer;
}
