# Technical Stack Evaluation

## 🎯 Selection Criteria
To support a public-facing, scalable gaming utility, the stack was evaluated against four core pillars:
1. **Real-Time Latency:** Must support <100ms sync.
2. **Cross-Platform Delivery:** Native performance on both mobile and web.
3. **AI Extensibility:** Ease of integration with LLM APIs (Gemini/OpenAI).
4. **Economic Scalability:** Low per-user overhead.

## 🏆 Final Recommendation: FlutterFlow + Firebase
After comparing **Bubble.io** (Rapid Prototyping) and **Supabase/Next.js** (Custom Scale), the **FlutterFlow + Firebase** stack was selected.

* **Native Performance:** Unlike web-wrapped builders, FlutterFlow provides high-performance native UX essential for live table play.
* **Firestore Real-Time DB:** Native support for the "Live HUD" features without requiring complex custom WebSocket management.
* **Deployment Agility:** Faster speed-to-market for a high-fidelity MVP.
