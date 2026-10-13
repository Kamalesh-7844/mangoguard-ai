# MangoGuard AI

MangoGuard AI is a premium agricultural intelligence workspace for mango leaf disease scouting. It guides a grower from image upload to a confidence-led signal, disease context, and practical next step. The web experience is built with React, Vite, Tailwind CSS, Framer Motion-ready interaction patterns, Lucide icons, and Recharts.

## What is implemented

The platform includes a responsive marketing landing page, leaf upload workflow with file validation and preview replacement, staged analysis states, prediction result presentation, confidence ring, six-class probability chart, dashboard history workspace, search and deletion controls, disease library detail views, model pipeline explanation, and a transparent simulation-mode treatment. The built-in Manus authentication boundary remains available for protected production wiring, while the preview experience is usable for product review without a login wall.

## ML layer: simulated by design

No trained TensorFlow/Keras model is included in this repository. The current product uses an isolated deterministic mock module at `server/mockPredict.ts`. It hashes the image bytes, selects one of six classes consistently, and produces a complete probability distribution that sums to 100. This makes the product behavior reproducible and gives the future model integration a narrow seam: replace `predictMock()` with a TensorFlow/Keras inference adapter while preserving the response contract.

The repository also includes `ml_service/main.py`, a small Python/FastAPI reference service showing the intended OpenCV/NumPy preprocessing contract. It is not spawned by the managed Node runtime. For a separate Python deployment, install `fastapi`, `uvicorn`, `opencv-python-headless`, and `numpy`, then run `uvicorn ml_service.main:app --reload`.

## Run locally

```bash
pnpm install
pnpm dev
```

The managed web project runs the React and server experience through the provided Node process. Type-check with `pnpm check` and run tests with `pnpm test`.

## API contract

The tRPC surface exposes `prediction.analyze`, `prediction.classes`, `history.list`, `history.remove`, and `diseases.list`. The prediction response keeps the requested keys: `prediction`, `confidence`, `status`, `probabilities`, and `recommendation`, with additional `severity`, `explanation`, and preprocessing metadata for the product UI. Database tables for users, diseases, and predictions are defined in `drizzle/schema.ts` and the generated migration is under `drizzle/`.

## Production handoff

Before using this for agronomic decisions, replace the simulation with a validated model, add model/version metadata to stored predictions, establish a carefully curated disease content review process, and validate recommendations with local agricultural experts. The current performance panel is explicitly illustrative and marked as simulated in the interface.
