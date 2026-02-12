# 🏛️ The Codex Empirica: Project 03
## Optimize Your Database with Indexes

This project is a deep dive into **Database Performance Tuning**. As part of the Codex series, I focus here on the empirical analysis of SQL execution plans, moving from inefficient "Full Table Scans" to high-speed indexed lookups.

---

## 📋 Implementation Checklist

### Phase 1: Performance Baseline
- [ ] **Task 1: System Audit**
  - [ ] Inspect schema and row counts.
  - [ ] Use `EXPLAIN` to document initial query costs (Full Table Scans).
  - [ ] Log baseline execution times.

### Phase 2: Single-Column Optimization
- [ ] **Task 2: Targeted B-Tree Indexing**
  - [ ] Apply index to `set_names` column.
  - [ ] **Assessment:** Verify transition from `type: ALL` to `type: ref`.
- [ ] **Task 3: Integrity & Profiling**
  - [ ] Deploy `UNIQUE` indexes for data hardening.
  - [ ] Use `SHOW PROFILE` to measure CPU/IO resource usage.

### Phase 3: Advanced Indexing Patterns
- [ ] **Task 4: Composite (Multi-Column) Design**
  - [ ] Implement indexes covering multiple query attributes.
  - [ ] Validate the **Left-Prefix Property** (column order efficiency).
- [ ] **Task 5: Relational Join Optimization**
  - [ ] Optimize cross-table performance by indexing Foreign Keys.
  - [ ] **Challenge:** Solve the Cumulative performance scenario.

### Phase 4: Final Validation
- [ ] **Graded Quiz:** Pass with a score of 80% or higher.
- [ ] **Certification:** Finalize the project and document results.

---

## 📊 Performance Benchmark
| Query Pattern | Strategy | Scan Type (Before) | Scan Type (After) | Result |
| :--- | :--- | :--- | :--- | :--- |
| Simple Filter | Single Index | `ALL` | `ref` | ✅ Faster |
| Multiple Filters | Composite Index | `ALL` | `range` | ✅ Optimized |
| Table Joins | FK Indexing | `ALL` | `eq_ref` | ✅ High Speed |

---

## 📂 Repository Structure
```bash
├── scripts/
│   ├── 01_baseline.sql       # Initial EXPLAIN analysis
│   ├── 02_create_indexes.sql  # Index implementation
│   └── 03_profiling.sql      # Performance measurement logs
├── notes/
│   └── optimization_log.md   # Detailed findings
└── README.md
