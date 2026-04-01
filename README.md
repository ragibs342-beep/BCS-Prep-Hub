const css = `
<style>
  :root { --primary: #2c3e50; --accent: #3498db; --success: #27ae60; --danger: #e74c3c; }
  body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: #f4f7f6; color: #333; line-height: 1.6; margin: 0; padding: 20px; }
  .container { max-width: 600px; margin: 0 auto; background: white; padding: 30px; border-radius: 12px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
  h1, h2 { color: var(--primary); text-align: center; }
  input { width: 100%; padding: 12px; margin: 10px 0; border: 1px solid #ddd; border-radius: 6px; box-sizing: border-box; }
  button { width: 100%; padding: 12px; background: var(--accent); color: white; border: none; border-radius: 6px; cursor: pointer; font-weight: bold; margin: 5px 0; transition: 0.3s; }
  button:hover { background: #2980b9; }
  .q-card { background: #fff; border-left: 5px solid var(--accent); padding: 15px; margin: 15px 0; border-radius: 4px; box-shadow: 0 2px 5px rgba(0,0,0,0.05); }
  .correct { background: #d4edda !important; border-left-color: var(--success); }
  .wrong { background: #f8d7da !important; border-left-color: var(--danger); }
  .timer-box { position: sticky; top: 10px; background: var(--primary); color: white; padding: 10px; border-radius: 5px; text-align: center; font-weight: bold; z-index: 100; }
  hr { border: 0; height: 1px; background: #eee; margin: 20px 0; }
  .result-item { background: #eee; padding: 10px; border-radius: 5px; margin-bottom: 5px; font-size: 0.9em; }
</style>
`;

// Update your routes to wrap the HTML in <div class="container"> and include ${css}
// Example for the Home Page:
app.get("/", (req, res) => {
  res.send(`
  ${css}
  <div class="container">
    <h1>🇧🇩 BCS Practice</h1>
    <input id="user" placeholder="Username">
    <input id="pass" type="password" placeholder="Password">
    <button onclick="login()">Login</button>
    <button onclick="signup()" style="background:#7f8c8d">Create Account</button>
  </div>
  <script>/* logic same as before */</script>
  `);
});

// For the Mock page, wrap each question in <div class="q-card">
