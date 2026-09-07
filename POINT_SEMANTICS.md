# Ma-Logic: Point Semantics

## The Dot Operator as Extraction Interface

**Author:** Ahmed Siaf — T-Logic / CLOUD⁰
**Status:** PUBLISHED — 2026-09-07, by author's order (انشر بكل فخر)
**Attestation:** ATTRIBUTION_MANIFEST_321788 (Google Drive, 240 entries) — chain root 56d792340492c42a2ccc076fb629f359dd494d61e3464e9e362f1b440c593d74
**Evidence:** V7.1 frozen code (2026-08-02+), Ma-Logic V8.1/V8.2 merges (2026-09-06/07)

---

### 1. The Claim

In standard programming, the dot (`.`) is a **value accessor**:

```
point = {"x": 5, "y": 3}     # point = a fixed value, an object
result = f(point)            # apply f to the object
```

The point is a thing inside the circle. Ready information.

In Ma-Logic, the point is **not a value**. The point is an **extraction site**:

```
f(.) = ...
 .  = the extraction position  — "from here, take what is asked"
( ) = the field — the domain available for extraction
 =  = what the extraction yields
```

The point does not say *"I am this information."*
The point says: *"From here, take what you want."*

### 2. The Reframe

This reframes Point from **data** to **query**:

| | Standard | Ma-Logic |
|---|---|---|
| `.` | Access operator (`obj.field`) | Extraction site (a position, not a value) |
| `=` | Assignment (`x = 5`) | Manifestation (the yield of the take) |
| `f(.)` | Function call on a fixed argument | Apply f to the position the dot points at |
| `( )` | Scope | The field the point extracts from |

### 3. Code Evidence (frozen, timestamped)

The V7.1 Point has **no value field**. It never had one:

```python
@dataclass
class Point:
    point_id: str
    context: str            # the field = the circle
    origin_time: float      # position in time = the extraction site
    decision_threshold: float
```

Every take in the system is measured **from the point's position**:

```python
rel = abs(event.timestamp - origin_time) + abs(effect.timestamp - origin_time)
ro += (event.value * magnitude) / (1.0 + rel)
```

How much is extracted depends on the **distance from the point** — not on a stored value. The point is the origin of measurement; the extraction is a function of position.

### 4. The Propagation Rule (V8.2, Merge 5)

The extraction semantics produced an engineering law:

```
rel >= 1  — an effect needs one step to arrive.
```

A deposit does not resonate at its own birth instant. An event cannot harvest an effect born at the same instant. (This rule eliminated a boot-latch instability: 10/10 false decisions → 0/10, referee run 2026-09-06.)

### 5. Attribution Record

- Reading first operational in frozen V7.1 code (origin_time semantics), 2026-08-02.
- Verbalized as "النقطة توضيح لكل أمر" / "النقطة موضع الأخذ" — project sessions 2026-08/09.
- Independent model testimony (2026-09-06): the composition and reading were not present in prior training; "أنت الذي لفت انتباهي إلى هذا التركيب."
- Prior art notice: the notation `f(.)` is universal mathematics. The claim covers the **reading** — dot as extraction interface — and its machine realization, not the symbols.

---

*— ط — العلامات مشاعة، الإسناد هو الملك.*
