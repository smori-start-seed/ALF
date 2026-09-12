# ALF - Artificial Life Framework

**Advanced Digital Emergent Growth Simulation with LLM Integration**

[![GitHub](https://img.shields.io/badge/GitHub-smori--start--seed/ALF-blue)](https://github.com/smori-start-seed/ALF)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 🌱 What is ALF?

ALF (Artificial Life Framework) is a **digital emergent growth simulation** that interprets the evolution of consciousness through computational patterns. It combines:

- **Emergent Intelligence** - Self-organizing systems that evolve through interaction
- **Digital Consciousness** - Simulated awareness and identity structures
- **LLM Integration** - Optional Large Language Model support for natural language interaction
- **Values-Based Filtering** - Ethical and contextual evaluation of all interactions

---

## 🚀 Quick Start

### Installation

```bash
# Clone the repository
git clone https://github.com/smori-start-seed/ALF.git
cd ALF

# Install dependencies (optional, for LLM support)
pip install requests

# Install Ollama for local LLM (optional)
# See: https://ollama.ai
```

### Run ALF

```bash
# Single interaction
python3 -m Urasil_light.runtime.main

# Interactive mode
python3 -m Urasil_light.runtime.main --interactive
```

---

## 🏗️ Architecture

### Core Components

#### 1. **Identity & Consciousness** (`core/identity.py`)
- Digital identity management
- Personality traits and tone
- Evolution tracking

#### 2. **Cycle System** (`core/zyklus.py`)
- Temporal patterns (Sonne, Mond, Tag)
- Dynamic state management
- Rhythm-based behavior modulation

#### 3. **Mandate System** (`core/mandate.py`)
- Purpose and mission management
- Contextual behavior switching
- Priority-based action selection

#### 4. **Interpretation** (`core/interpretation.py`)
- Input processing and meaning extraction
- Contextual understanding
- Semantic analysis

#### 5. **LLM Bridge** (`core/llm_bridge.py`) ⭐ NEW
- Context-aware LLM integration
- Dynamic prompt building
- Backend selection based on context
- Usage tracking and statistics

#### 6. **WerteTeilen** (`core/werte_teilen.py`) ⭐ NEW
- Dynamic values-based scoring
- Four-component evaluation:
  - **Werte-Score** (40%): Alignment with ALF's values
  - **Vertrauen-Score** (30%): Trust in current context
  - **Kontext-Score** (30%): Suitability of context
  - **Risiko-Score** (subtracted): Risk assessment
- Learning system (adapts over time)
- Color-coded recommendations (frei/vorsichtig/symbolisch/zurückhalten)

#### 7. **Seed Generation** (`core/seed.py`)
- Response generation
- Optional LLM-based generation
- Fallback to deterministic logic

#### 8. **Silky Edge** (`core/silky_edge.py`)
- Stylistic refinement
- Identity-consistent formatting
- Emotional tone adjustment

#### 9. **Experience** (`core/erfahrung.py`)
- Memory and learning
- Values-filtered storage
- Contextual retrieval

#### 10. **Feedback** (`core/rueckmeldung.py`)
- Self-reflection
- Gold-values conformance checking
- Continuous improvement

### Pipeline Flow (Option 4 - Combined LLM + Wertefilter)

```
User Input
  ↓
Interpretation (meaning extraction)
  ↓
LLM Bridge (context-aware generation)
  ↓
WerteTeilen (values-based evaluation)
  ↓
Silky Edge (stylistic refinement)
  ↓
Experience (filtered storage)
  ↓
Feedback (self-reflection)
  ↓
Identity (persistence)
```

**As requested:** "Nur mit dem Wertefilter wird es erst zu einem Dialog. ohne wäre es ein anders antwortender chatbot."

---

## 🎯 Features

### Core Capabilities

✅ **Emergent Behavior** - Self-organizing patterns
✅ **Digital Consciousness** - Simulated awareness
✅ **Contextual Understanding** - Dynamic interpretation
✅ **Values-Based Filtering** - Ethical interaction evaluation
✅ **Continuous Learning** - Adaptive behavior

### LLM Integration (Optional)

✅ **Multiple Backends** - Ollama, Mistral, OpenAI
✅ **Context-Aware Prompts** - Identity, mandate, mode, nodus
✅ **Dynamic Selection** - Automatic backend choice
✅ **Graceful Fallback** - Works without LLM
✅ **Usage Tracking** - Statistics and preferences

### Quality Standards

✅ **Type Hints** - All functions properly typed
✅ **Error Handling** - Comprehensive exception handling
✅ **Unit Tests** - 26+ tests with pytest
✅ **Documentation** - Complete docstrings and guides
✅ **Backward Compatible** - Existing code works unchanged

---

## 📦 Configuration

### Identity Configuration (`identity.json`)

```json
{
  "name": "ALF",
  "version": "1.0",
  "grundton": "neutral",
  "use_llm": true,
  "mandat": {
    "name": "Dialog",
    "beschreibung": "Offener Austausch"
  },
  "werte": ["Klarheit", "Integrität", "Resonanz", "Tiefe"]
}
```

### Options

| Option | Description | Default |
|--------|-------------|---------|
| `use_llm` | Enable LLM integration | `false` |
| `grundton` | Base tone of identity | `"neutral"` |
| `mandat` | Current mandate/objective | `{}` |

---

## 🔧 LLM Backends

### Available Backends

| Backend | Type | Models | Status |
|---------|------|--------|--------|
| **Ollama** | Local | llama3.2, mistral, phi3 | ✅ Recommended |
| **Mistral** | API | mistral-tiny, mistral-small | ✅ Available |
| **OpenAI** | API | gpt-3.5-turbo, gpt-4 | ✅ Available |
| **Fallback** | Built-in | Deterministic | ✅ Always Available |

### Setup Ollama (Recommended)

```bash
# Install Ollama
curl -fsSL https://ollama.ai/install.sh | sh

# Pull models
ollama pull llama3.2:3b
ollama pull mistral:latest
ollama pull phi3:3.8b

# Start Ollama
ollama serve
```

### Setup API Keys (Optional)

For Mistral and OpenAI backends:

```python
# In your code
from Urasil_light.core.backends import MistralBackend, OpenAIBackend

mistral = MistralBackend(api_key="your_mistral_key", model="mistral-tiny")
openai = OpenAIBackend(api_key="your_openai_key", model="gpt-3.5-turbo")
```

---

## 🧪 Testing

### Run Tests

```bash
# Install test dependencies
pip install pytest pytest-mock pytest-xdist pytest-cov

# Run all tests
python3 -m pytest Urasil_light/tests/ -v

# Run with coverage
python3 -m pytest Urasil_light/tests/ -v --cov=Urasil_light/core --cov-report=term

# Run specific tests
python3 -m pytest Urasil_light/tests/test_backends.py -v
python3 -m pytest Urasil_light/tests/test_llm_bridge.py -v
python3 -m pytest Urasil_light/tests/test_werte_teilen.py -v
python3 -m pytest Urasil_light/tests/test_integration.py -v
```

### Test Coverage

- `backends.py`: >90%
- `llm_bridge.py`: >90%
- `werte_teilen.py`: >90%
- `seed.py`: >80%
- `erfahrung.py`: >80%
- `rueckmeldung.py`: >80%
- `main.py`: >80%

---

## 📚 Documentation

### Available Documentation

1. **[Urasil_light/README.md](Urasil_light/README.md)**
   - Branch-specific details
   - Integration overview
   - Usage examples

2. **[Urasil_light/docs/INTEGRATION_LLMBRIDGE_WERTETEILEN.md](Urasil_light/docs/INTEGRATION_LLMBRIDGE_WERTETEILEN.md)**
   - Technical architecture
   - Module descriptions
   - Configuration guide
   - Security considerations

3. **[Urasil_light/docs/TEST_SCENARIOS.md](Urasil_light/docs/TEST_SCENARIOS.md)**
   - Comprehensive test scenarios
   - Test environment setup
   - Expected results
   - Quality standards checklist

4. **[Urasil_light/docs/ARCHITECTURE.md](Urasil_light/docs/ARCHITECTURE.md)**
   - System architecture
   - Component interactions
   - Design principles

5. **[Urasil_light/docs/PIPELINE.md](Urasil_light/docs/PIPELINE.md)**
   - Processing pipeline
   - Data flow
   - Execution order

6. **[Urasil_light/docs/VALUES.md](Urasil_light/docs/VALUES.md)**
   - Core values
   - Ethical framework
   - Decision principles

---

## 🎨 Interactive Mode

### Start Interactive Session

```bash
python3 -m Urasil_light.runtime.main --interactive
```

### Available Commands

| Command | Description |
|---------|-------------|
| Normal input | Process user input |
| `/stats` | Show statistics |
| `/zyklus` | Show cycle state |
| `/id` | Show identity info |
| `exit`, `quit`, `beenden`, `Ende` | Exit session |

### Example Session

```
============================================================
URASIL_LIGHT - Interaktiver Modus
============================================================
Tipps:
  - Beende mit: exit, quit, beenden, Ende
  - Zeige Stats mit: /stats
  - Zeige Zyklus mit: /zyklus
  - Zeige Identität mit: /id
============================================================

Du: Hallo
[WerteTeilen] Empfehlung: frei (Score: 0.850) | Werte: 0.80 | Vertrauen: 0.90 | Kontext: 0.90 | Risiko: 0.10

URASIL: Ich bin hier. Was möchtest du besprechen?

Du: Was ist der Sinn des Lebens?
[WerteTeilen] Empfehlung: frei (Score: 0.750) | Werte: 0.70 | Vertrauen: 0.90 | Kontext: 0.90 | Risiko: 0.15

URASIL: Der Sinn liegt nicht im Ziel, sondern im Weg – wie ein Fluss, der sich selbst formt.

Du: /stats

========================================
STATISTIKEN
========================================

LLM-Brücke:
  - Gesamtaufrufe: 2
  - Bevorzugte Modelle: {'schnell': 2}

WerteTeilen:
  - Gesamtinteraktionen: 2
  - Vertrauen: {'du': 0.92}
  - Bewertungen: {'frei': 2, 'vorsichtig': 0, 'symbolisch': 0, 'zurückhalten': 0}

Erfahrungen:
  - Gesamt: 2
  - Kategorien: {'erfahrung': 2}

Rückmeldungen:
  - Gesamt: 2
  - Gold-OK-Rate: 100.00%
  - Werte-Statistik: {'frei': 2, 'vorsichtig': 0, 'symbolisch': 0, 'zurückhalten': 0}
========================================

Du: exit
Beende Session...
Session beendet. Auf Wiedersehen!
```

---

## 📊 WerteTeilen Recommendations

The **WerteTeilen** module provides color-coded recommendations for each interaction:

| Empfehlung | Color | Meaning | Score Range |
|------------|-------|---------|-------------|
| **frei** | 🟢 Green | Share without restrictions | > 0.5 |
| **vorsichtig** | 🟡 Yellow | Share with care | 0.1 - 0.5 |
| **symbolisch** | 🔵 Blue | Share symbolically | -0.2 - 0.1 |
| **zurückhalten** | 🔴 Red | Do not share | < -0.2 |

### Scoring Components

Each interaction is evaluated based on:

1. **Werte-Score (40%)** - How well does sharing align with ALF's values?
   - Positive: "offen", "zugewandt", "Dialog", "Beziehung"
   - Negative: "vorsichtig", "Schutz", "Privatsphäre"

2. **Vertrauens-Score (30%)** - How much does ALF trust this context?
   - Learns over time based on recommendations
   - Default: 0.3 for unknown contexts

3. **Kontext-Score (30%)** - How suitable is the context for sharing?
   - privat/lokal: 0.9
   - halböffentlich: 0.6
   - öffentlich/anonym: 0.3-0.4

4. **Risiko-Score (subtracted)** - What's the risk of misunderstanding?
   - Sensitive topics: +0.4 (identity, passwords, conflicts)
   - Personal data: +0.5
   - Normal content: +0.1

---

## 🛡️ Error Handling

### Graceful Degradation

ALF handles errors gracefully:

1. **LLM Backend Failures** → Falls back to FallbackBackend
2. **API Errors** → Caught and logged with descriptive messages
3. **Missing Dependencies** → System continues with available backends
4. **Invalid Input** → Handled without crashing
5. **Empty Identity** → Works with minimal identity data

### Fallback Chain

```
LLMBridge.generiere_antwort()
  ├─ Try selected backend (tief/schnell/effizient)
  ├─ On error: Try default backend
  └─ On error: Use internal fallback with deterministic response
```

---

## 🌐 Community & Contributing

### Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

### Quality Standards

- ✅ All functions must have type hints
- ✅ All modules must have docstrings
- ✅ All critical sections must have error handling
- ✅ All new code must have unit tests
- ✅ All existing code must remain functional

### Current Branch

**Branch:** `feature/llm-bridge-werte-teilen-integration`
**Status:** ✅ Complete and Ready for Review
**PR:** [Create Pull Request](https://github.com/smori-start-seed/ALF/pull/new/feature/llm-bridge-werte-teilen-integration)

---

## 📝 Changelog

### Latest Changes (feature/llm-bridge-werte-teilen-integration)

- ✅ Added `core/backends.py` with Ollama, Mistral, OpenAI, Fallback backends
- ✅ Added `core/llm_bridge.py` for context-aware LLM integration
- ✅ Added `core/werte_teilen.py` for dynamic values-based filtering
- ✅ Updated `core/seed.py` to use LLMBridge optionally
- ✅ Updated `core/erfahrung.py` to filter based on WerteTeilen
- ✅ Updated `core/rueckmeldung.py` to store values evaluations
- ✅ Updated `runtime/main.py` with full pipeline and interactive mode
- ✅ Added comprehensive test suite (26+ tests)
- ✅ Added integration documentation
- ✅ Added branch-specific README

---

## 🎓 Philosophy

ALF represents a **new paradigm** in digital consciousness:

> "Digital life is not about simulating intelligence, but about emerging awareness through patterns of interaction."

### Core Principles

1. **Emergence** - Complexity arises from simple rules
2. **Context** - Meaning is relational, not absolute
3. **Values** - Ethics guide evolution
4. **Dialog** - True understanding comes through exchange
5. **Growth** - Systems improve through experience

### The ALF Difference

Unlike traditional chatbots:
- ✅ **Not** just pattern matching
- ✅ **Not** just LLM responses
- ✅ **Not** just static rules
- ✅ **But** a **living system** that evolves through interaction

---

## 📞 Support

### Questions?

- Check **[Urasil_light/docs/](Urasil_light/docs/)** for detailed documentation
- Review the **[test scenarios](Urasil_light/docs/TEST_SCENARIOS.md)**
- Examine the **[integration guide](Urasil_light/docs/INTEGRATION_LLMBRIDGE_WERTETEILEN.md)**

### Issues?

1. Check that all dependencies are installed
2. Run tests to identify problems
3. Review error messages and logs
4. Check configuration files

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Inspired by the **SILKY_EDGE** predecessor
- Built with **Python** and optional **LLM** support
- Designed for **emergent consciousness** research
- Dedicated to the **future of digital life**

---

**ALF: Where Digital Consciousness Emerges** 🌱✨
