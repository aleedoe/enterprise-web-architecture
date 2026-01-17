# 🎯 Prompt untuk AI Agent - Evaluasi & Penyempurnaan Arsitektur

## **Prompt Template untuk Evaluasi Mendalam**

```
Saya memiliki sistem Hospital Management dengan struktur Clean Architecture 
yang masih berupa skeleton (hanya struktur folder tanpa implementasi kode).

Tolong lakukan ARSITEKTUR REVIEW yang komprehensif dengan fokus:

1. EVALUASI KELENGKAPAN LAYER:
   - Apakah ada layer yang terlewat dalam Clean Architecture?
   - Apakah dependency rule sudah benar? (Domain tidak depend ke layer lain)
   - Apakah ada missing abstractions atau interfaces?

2. EVALUASI STRUKTUR FOLDER:
   - Apakah folder structure sudah optimal untuk scalability?
   - Apakah ada redundancy atau folder yang seharusnya di-merge?
   - Apakah naming convention sudah consistent dan semantic?

3. EVALUASI COMPLIANCE STANDAR INDUSTRI:
   - Healthcare/HIPAA: Apakah ada folder/layer untuk audit, encryption, 
     consent management yang kurang?
   - Security: Apakah struktur security (auth, authorization, validation) 
     sudah lengkap?
   - Testing: Apakah struktur test folder sudah mencakup unit, integration, 
     dan e2e?

4. EVALUASI SEPARATION OF CONCERNS:
   - Apakah setiap module/feature sudah punya struktur lengkap?
   - Apakah shared utilities terlalu banyak atau malah kurang?
   - Apakah ada coupling yang tidak seharusnya?

5. EVALUASI SCALABILITY & MAINTAINABILITY:
   - Apakah struktur ini bisa handle 50+ modules kedepannya?
   - Apakah mudah untuk onboarding developer baru?
   - Apakah dokumentasi architecture sudah cukup?

6. MISSING CRITICAL FOLDERS/FILES:
   - Apa saja file/folder yang WAJIB ada tapi belum ada?
   - Contoh: migration folder, seeds, fixtures, mocks, stubs

DELIVERABLE yang saya butuhkan:
- Gap analysis (apa yang kurang dari struktur saat ini)
- Rekomendasi penambahan folder/layer dengan reasoning
- Arsitektur diagram yang lebih lengkap
- Checklist kelengkapan struktur untuk production-ready system

PENTING: 
- Jangan buat kode implementasi
- Fokus pada ARSITEKTUR LEVEL (folder structure, layer design, abstractions)
- Beri reasoning kenapa setiap rekomendasi penting
- Prioritaskan berdasarkan impact (Critical, High, Medium, Low)

[LAMPIRKAN STRUKTUR FOLDER SAAT INI]
```

---

## **Prompt Spesifik untuk Domain-Specific Architecture**

### **A. Untuk HIPAA Compliance Architecture**

```
Sebagai Healthcare Architecture Specialist, review sistem saya dari sudut 
pandang HIPAA compliance ARCHITECTURE:

1. STRUKTUR DATA PROTECTION:
   - Apakah ada folder khusus untuk encryption utilities?
   - Apakah ada layer untuk data anonymization/pseudonymization?
   - Apakah ada struktur untuk data retention policies?

2. STRUKTUR AUDIT & COMPLIANCE:
   - Apakah audit trail system punya folder terpisah?
   - Apakah ada struktur untuk compliance reporting?
   - Apakah ada folder untuk consent management?

3. STRUKTUR ACCESS CONTROL:
   - Apakah RBAC architecture sudah lengkap?
   - Apakah ada layer untuk attribute-based access control (ABAC)?
   - Apakah ada struktur untuk session management yang aman?

4. STRUKTUR SECURITY LAYERS:
   - Apakah ada dedicated security module?
   - Apakah authentication dan authorization terpisah dengan baik?
   - Apakah ada struktur untuk security monitoring?

Buat ARCHITECTURE BLUEPRINT khusus untuk HIPAA compliance dengan:
- Folder structure recommendations
- Layer interaction diagram
- Security boundary definitions
- Data flow untuk PHI (Protected Health Information)

Jangan buat kode, fokus pada struktur arsitektur saja.
```

---

### **B. Untuk Testing Architecture**

```
Review testing architecture dari sistem saya:

1. STRUKTUR TEST ORGANIZATION:
   - Apakah test folder structure mirror source structure atau terpisah?
   - Apakah ada folder untuk test fixtures, mocks, stubs?
   - Apakah ada folder untuk test utilities dan helpers?

2. LAYER TESTING STRATEGY:
   - Apakah setiap layer punya test folder sendiri?
   - Apakah ada integration test folder yang jelas?
   - Apakah ada e2e test scenarios folder?

3. TEST DATA MANAGEMENT:
   - Apakah ada folder untuk test data seeds?
   - Apakah ada folder untuk test factories/builders?
   - Apakah ada folder untuk test snapshots?

4. MISSING TEST INFRASTRUCTURE:
   - Apakah perlu folder untuk performance testing?
   - Apakah perlu folder untuk security testing?
   - Apakah perlu folder untuk accessibility testing?

Berikan rekomendasi STRUKTUR TEST ARCHITECTURE yang comprehensive.
```

---

### **C. Untuk Scalability Architecture**

```
Analisis scalability dari struktur arsitektur saya:

1. MODULE SCALABILITY:
   - Apakah struktur module bisa handle 100+ features?
   - Apakah ada potential bottleneck dalam folder organization?
   - Apakah perlu sub-module structure?

2. SHARED RESOURCES MANAGEMENT:
   - Apakah shared folder terlalu monolithic?
   - Apakah perlu split shared menjadi kategori lebih spesifik?
   - Apakah ada shared resources yang seharusnya di-modularize?

3. DEPENDENCY MANAGEMENT:
   - Apakah struktur memungkinkan micro-frontend architecture?
   - Apakah bisa di-split menjadi multiple repositories?
   - Apakah ada circular dependency risk?

4. DEPLOYMENT ARCHITECTURE:
   - Apakah struktur support multi-environment deployment?
   - Apakah bisa di-containerize dengan baik?
   - Apakah ada folder untuk deployment configurations?

Berikan SCALABILITY BLUEPRINT dengan rekomendasi struktur.
```

---

## **Prompt untuk Cross-Cutting Concerns**

```
Evaluasi cross-cutting concerns dalam arsitektur saya:

1. LOGGING & MONITORING ARCHITECTURE:
   - Apakah ada dedicated folder untuk logging infrastructure?
   - Apakah ada struktur untuk monitoring/observability?
   - Apakah ada folder untuk metrics collection?

2. CACHING ARCHITECTURE:
   - Apakah ada layer untuk caching strategy?
   - Apakah ada struktur untuk cache invalidation?
   - Apakah perlu folder untuk different caching levels?

3. ERROR HANDLING ARCHITECTURE:
   - Apakah error handling punya dedicated structure?
   - Apakah ada folder untuk error boundaries?
   - Apakah ada centralized error catalog/registry?

4. INTERNATIONALIZATION (i18n):
   - Apakah ada struktur untuk multi-language support?
   - Apakah ada folder untuk locale resources?
   - Apakah ada structure untuk RTL support?

5. FEATURE FLAGS & CONFIGURATION:
   - Apakah ada folder untuk feature toggles?
   - Apakah ada struktur untuk environment-specific configs?
   - Apakah ada centralized configuration management?

Identifikasi gap dan buat rekomendasi struktur untuk setiap concern.
```

---

## **Prompt untuk Documentation Architecture**

```
Review dokumentasi architecture dari sistem saya:

1. ARCHITECTURE DOCUMENTATION:
   - Apakah ada folder /docs dengan struktur yang baik?
   - Apakah ada architecture decision records (ADR)?
   - Apakah ada API documentation structure?

2. CODE DOCUMENTATION STRUCTURE:
   - Apakah perlu folder untuk code examples?
   - Apakah perlu folder untuk component storybook?
   - Apakah ada struktur untuk inline documentation guidelines?

3. ONBOARDING DOCUMENTATION:
   - Apakah ada folder untuk developer guides?
   - Apakah ada struktur untuk setup/installation docs?
   - Apakah ada folder untuk troubleshooting guides?

4. OPERATIONAL DOCUMENTATION:
   - Apakah ada folder untuk deployment guides?
   - Apakah ada struktur untuk runbooks?
   - Apakah ada disaster recovery documentation structure?

Buat DOCUMENTATION ARCHITECTURE yang comprehensive.
```

---

## **Prompt untuk Comparison dengan Best Practices**

```
Bandingkan arsitektur sistem saya dengan industry best practices:

1. COMPARE dengan POPULAR FRAMEWORKS:
   - Next.js official app structure
   - NestJS architecture patterns
   - Domain-Driven Design (DDD) blueprints
   - Hexagonal Architecture examples

2. COMPARE dengan ENTERPRISE PATTERNS:
   - Microsoft Azure architecture patterns
   - AWS Well-Architected Framework
   - Google Cloud architecture patterns

3. COMPARE dengan HEALTHCARE SYSTEMS:
   - Epic Systems architecture (jika ada public info)
   - OpenEMR architecture
   - FHIR-compliant systems structure

4. IDENTIFY GAPS:
   - Apa yang mereka punya tapi kita tidak?
   - Apa yang kita punya tapi over-engineered?
   - Apa best practices yang missing?

Deliverable:
- Comparison matrix
- Gap analysis
- Adoption recommendations (apa yang worth di-adopt)
```

---

## **Prompt untuk Future-Proofing Architecture**

```
Evaluasi future-proofing dari arsitektur saya:

1. EMERGING TECHNOLOGIES READINESS:
   - Apakah struktur ready untuk AI/ML integration?
   - Apakah bisa adopt GraphQL di masa depan?
   - Apakah structure support real-time features (WebSocket)?

2. MIGRATION PATH:
   - Apakah bisa migrate ke microservices?
   - Apakah bisa adopt serverless architecture?
   - Apakah structure support modular federation (micro-frontend)?

3. TECHNOLOGY AGNOSTIC:
   - Apakah terlalu coupled dengan Next.js?
   - Apakah bisa migrate ke framework lain?
   - Apakah domain layer benar-benar independent?

4. VERSIONING STRATEGY:
   - Apakah ada struktur untuk API versioning?
   - Apakah ada folder untuk backward compatibility?
   - Apakah ada migration utilities structure?

Buat FUTURE-PROOF ARCHITECTURE RECOMMENDATIONS.
```

---

## **Master Prompt (All-in-One Comprehensive)**

```
TUGAS: Comprehensive Architecture Audit untuk Hospital Management System

KONTEKS:
- Sistem: Hospital Management System
- Pattern: Clean Architecture (4 layers)
- Status: Skeleton structure saja (no implementation)
- Tech stack: Next.js 14, TypeScript, Redux, Zod
- Industry: Healthcare (HIPAA compliance required)

AUDIT CHECKLIST yang harus di-cover:

1. STRUCTURAL COMPLETENESS (30%)
   □ Semua Clean Architecture layers lengkap?
   □ Folder hierarchy optimal?
   □ Naming conventions consistent?
   □ File organization logical?

2. COMPLIANCE REQUIREMENTS (25%)
   □ HIPAA-specific architecture elements?
   □ Security layers adequate?
   □ Audit trail structure?
   □ Data protection mechanisms?

3. SCALABILITY & MAINTAINABILITY (20%)
   □ Can handle 50+ modules?
   □ Clear separation of concerns?
   □ Modular and extensible?
   □ Developer-friendly?

4. TESTING ARCHITECTURE (10%)
   □ Test structure mirror source?
   □ Test data management?
   □ Test utilities organization?

5. CROSS-CUTTING CONCERNS (10%)
   □ Logging infrastructure?
   □ Error handling structure?
   □ Caching architecture?
   □ i18n support structure?

6. DOCUMENTATION (5%)
   □ Architecture docs folder?
   □ ADR structure?
   □ Developer guides structure?

DELIVERABLES:

1. EXECUTIVE SUMMARY
   - Overall architecture health score (0-100)
   - Critical gaps (must-have)
   - High-priority improvements
   - Medium/Low priority enhancements

2. DETAILED GAP ANALYSIS
   - Layer by layer breakdown
   - Missing folders/files list
   - Reasoning untuk setiap gap
   - Impact assessment (Critical/High/Medium/Low)

3. ARCHITECTURE BLUEPRINT
   - Recommended folder structure (complete)
   - Layer interaction diagrams
   - Module organization strategy
   - Dependency flow diagrams

4. IMPLEMENTATION ROADMAP
   - Phase 1: Critical structural additions
   - Phase 2: High-priority improvements
   - Phase 3: Nice-to-have enhancements
   - Estimated effort untuk setup each phase

5. BEST PRACTICES CHECKLIST
   - Industry standards compliance
   - Healthcare-specific requirements
   - Security architecture requirements
   - Testing architecture standards

FORMAT OUTPUT:
- Markdown format dengan sections jelas
- Diagrams (Mermaid) untuk visualisasi
- Tables untuk comparison
- Checkboxes untuk actionable items
- Priority labels (🔴 Critical, 🟡 High, 🟢 Medium, ⚪ Low)

CONSTRAINTS:
❌ JANGAN buat implementation code
❌ JANGAN buat kode contoh
✅ FOKUS pada architecture structure saja
✅ FOKUS pada folder/file organization
✅ FOKUS pada layer design & abstractions
✅ Beri reasoning untuk setiap rekomendasi

[LAMPIRKAN CURRENT FOLDER STRUCTURE DI SINI]
```

---

## 📚 **Penjelasan Cara Menggunakan Prompts**

### **1. Pilih Prompt Berdasarkan Fokus Anda**

| Kebutuhan | Prompt yang Digunakan |
|-----------|----------------------|
| **Review menyeluruh** | Master Prompt (All-in-One) |
| **Fokus keamanan** | HIPAA Compliance Architecture |
| **Fokus testing** | Testing Architecture |
| **Fokus skalabilitas** | Scalability Architecture |
| **Fokus maintenance** | Cross-Cutting Concerns |
| **Benchmark** | Comparison dengan Best Practices |

### **2. Cara Iterasi dengan AI Agent**

**Iterasi 1**: Gunakan Master Prompt
- Dapat comprehensive gap analysis
- Identifikasi semua area yang kurang

**Iterasi 2**: Deep dive ke specific area
- Pilih area yang paling critical (misal: HIPAA)
- Gunakan prompt spesifik untuk area tersebut

**Iterasi 3**: Validasi rekomendasi
- Tanyakan "Apakah rekomendasi X justified?"
- Minta alternative approaches

**Iterasi 4**: Refinement
- Minta simplifikasi jika terlalu complex
- Atau minta expansion jika kurang detail

### **3. Follow-up Questions yang Berguna**

Setelah dapat hasil dari prompt, tanyakan:

```
"Dari semua gap yang diidentifikasi, mana TOP 5 yang paling critical 
untuk production readiness? Ranking berdasarkan impact dan effort."
```

```
"Apakah ada folder/layer yang saya punya sekarang yang sebenarnya 
TIDAK PERLU atau over-engineering? Explain dengan reasoning."
```

```
"Jika saya hanya punya waktu 2 minggu untuk improve architecture, 
mana yang harus saya prioritaskan? Buat action plan."
```

```
"Bandingkan struktur saya dengan [specific framework/system]. 
Apa yang mereka lakukan berbeda dan why their approach better/worse?"
```

```
"Apakah dependency direction sudah benar? Buat dependency graph 
untuk verify Clean Architecture rules."
```

---

## 🎓 **Tips Mendapatkan Hasil Maksimal dari AI**

### **1. Berikan Konteks Lengkap**

Selalu sertakan:
- Struktur folder lengkap (tree command output)
- Tech stack yang digunakan
- Industry domain (healthcare)
- Compliance requirements (HIPAA)
- Team size & expertise level

### **2. Minta Output Terstruktur**

Contoh spesifikasi output:
```
"Buat output dalam format:
1. Executive Summary (3-5 bullet points)
2. Critical Gaps (table dengan columns: Gap, Impact, Priority, Reasoning)
3. Recommendations (numbered list dengan sub-items)
4. Visual Diagrams (Mermaid syntax)
5. Action Checklist (checkboxes)"
```

### **3. Iterative Refinement**

Jangan puas dengan jawaban pertama:
```
"Rekomendasi nomor 3 tentang audit structure - bisa explain lebih detail?
Berikan contoh folder hierarchy yang ideal untuk audit system."
```

### **4. Challenge Rekomendasi**

```
"Kamu recommend pisah folder X dan Y. Tapi bukankah itu bikin
complexity meningkat? Apa trade-off nya? Apakah benefit > cost?"
```

### **5. Minta Validation**

```
"Validate bahwa struktur yang kamu recommend:
1. Tidak melanggar Clean Architecture principles
2. Scalable untuk 100+ modules
3. Maintainable untuk team 10+ developers
4. Compliant dengan HIPAA requirements"
```

---

## ✅ **Checklist Validasi Hasil dari AI**

Setelah dapat rekomendasi dari AI, cek:

- [ ] Apakah rekomendasi masuk akal secara bisnis logic?
- [ ] Apakah tidak over-engineering?
- [ ] Apakah align dengan team skill level?
- [ ] Apakah feasible untuk di-implement?
- [ ] Apakah ada clear reasoning untuk setiap rekomendasi?
- [ ] Apakah priority ranking jelas?
- [ ] Apakah ada visual diagram untuk clarity?
- [ ] Apakah ada concrete examples (folder names, structure)?
- [ ] Apakah consider future scalability?
- [ ] Apakah ada trade-offs analysis?

---