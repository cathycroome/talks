# Sankey flow diagram of attended talks

- Talks are from September 2026 to last commit date
- Categorised by field, subfield, topic and themes
- <https://cathycroome.github.io/talks/>


## Files

- `export.csv` is a CSV of talks attended with user-inputted speaker, talk title, and associated institution, as well as user-defined fields, subfields and topic tags
- `index.html` is the HTML of the interactive sankey flow diagram - visualisation of the data using Claude
  - contains the theme classifications


## To test locally

```bash
cd talks
python3 -m http.server 8000
```

Open <http://localhost:8000>


## Hide singles

- "Hide singles" button removes any node from the chart that is only associated with one talk (applies across main field, subfield, and topic tag)
- Removing a node and its talk can cause other nodes to drop to one talk so the filter iterates until the chart stabilises
- "Show singles" restores the full chart


## Links to talks

Linked videos may be a similar talk (same title) in another venue

## More info on attempt to classify research into fields and subfields
<details>
<summary>See rules of thumb</summary>

> **NB:** Classifications are not necessarily how speakers would describe their own research. They reflect an attempt to learn how different fields and subfields define themselves & disagreement is welcome.

### Step 1: Main Field

Broad home of the talk, classified by what the main claim is about and the approach taken

**Is the central question conceptual or empirical?**

- Conceptual → usually Philosophy [concept]
- Empirical → go to next question

**What is being studied?**

- Mental processes and behaviour, usually in humans and without neural measures → Psychology [mind]
- The structure or function of the nervous system, including neural data and behaviour studied to understand neural mechanisms → Neuroscience [brain]
- Computing systems themselves, such as models, algorithms, and architectures → Computer Science [compute]

**Is it hard to place in just one of the above?**

- The central claim concerns cognition and spans several fields → consider Cognitive Science [concept / mind / brain / compute]
  - Reserved for talks whose central contribution doesn't fit neatly within one main field. Many talks could technically qualify so it's used sparingly.
- There are multiple central claims (e.g. a synthesis of several research projects) → tag multiple main fields, also sparingly

### Step 2: Subfield

Many talks are tagged with more than one subfield. Subfields are defined along different axes (what is studied, at what level, with what approach), and any combination can apply. These are rules of thumb, not strict boundaries.

**Neuroscience**

*What was studied?*

- Cognition (perception, attention, memory, language, decision-making) linked to neural measures, typically in healthy or sub-clinical human populations → **Cognitive Neuroscience**
- Brain or cognitive development in infants, children, and adolescents → **Developmental Neuroscience** (often alongside Cognitive Neuroscience)
- Mechanisms of disease or disorder in patients → **Clinical Neuroscience**
- Animal behaviour tied to a neural or hormonal mechanism → **Behavioural Neuroscience**
- How stimulus features are encoded at successive stages of processing → **Sensory Neuroscience**

*At what level?*

- Microscopic level (neurotransmitters, receptors, ion channels, neurons, glial cells) → **Molecular and Cellular Neuroscience**
- Circuits and large-scale brain networks, including aggregated activity (e.g. fMRI, EEG) → **Systems Neuroscience**

*What approach or aim?*

- To computationally or mathematically model brain structure or function, at any level from biophysical to abstract → **Computational (or Theoretical) Neuroscience**
- The clinical application of neuroscience research to develop treatments for nervous systems disorders → **Translational neuroscience**

**Psychology**

Typically behaviour is analysed to target cognitive processes, without neural recordings

*What is studied?*

- Cognition in healthy or sub-clinical human populations → **Cognitive Psychology**
- Mental health, disorders, or clinical populations → **Clinical Psychology**
- Cognition or behaviour across the lifespan → **Developmental Psychology**
- Human learning, typically in educational settings → **Educational Psychology**

**Philosophy**

Subfields are of two kinds, which sit at the same level and are often combined:

- Domain branches (the default), defined by what is being examined: **Philosophy of Mind**, **Philosophy of Science**, **Philosophy of Technology**
- Core branches, added when the domain alone doesn't capture the talk, defined by the kind of question being asked, e.g.
  - What exists, and what is it? → **Metaphysics**
  - What follows from what? → **Logic**
  - **Ethics** is an exception and is tagged as a topic rather than a subfield so it can link talks across fields

**Computer Science**

- Most exposure to Computer Science is through Artificial Intelligence
- Machine learning is generally seen as the method and is tagged in theme rather than subfield

**Cognitive Science**

- Most Cognitive Science subfields are shared with the other fields (Cognitive Neuroscience, Cognitive Psychology, Philosophy of Mind, Artificial Intelligence, etc.)
- Computational modelling of cognition that isn't directly modelling the nervous system → **Computational Cognitive Science**

### Step 3: Topic tags

- Meant to be quick way of tagging a few extra pieces of information about a talk
- Chosen to track specific methods / applications / sub-subfields / conditions / modalities, or to link talks across fields
- Unlikely to be how the speaker would tag their own research, and not close to exhaustive

### Step 4: Themes

- Tags are assigned to thematic groupings and these change based on talks that are added
- This level of classification is generated with Claude; not a priority since themes could be split in many different ways, but having it helps with visual organisation
</details>