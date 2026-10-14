# Examples

`demo-site/` is **TaskNest**, a tiny fictional site (4 static pages) built with deliberate UX-psychology flaws, so the skill has something to find without auditing anyone's real product.

`tasknest-audit.md` is the report the skill produced after walking through it in a browser. Run it yourself:

```bash
python3 -m http.server 8765 --directory examples/demo-site
```

then ask Claude: "audit http://localhost:8765 with the ux-psychology-audit skill".
