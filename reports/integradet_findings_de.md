# Integrierte inhaltliche Beschreibung

**Stand:** Explorative Analysephase (Juni 2026)

## Gesamtbefund

Die Analysen zeigen, dass das Korpus weniger durch einzelne Themen als durch **Register, Textfunktionen und Produktionsmodi** strukturiert wird. Wiederkehrende Trennachsen sind formale Verdichtung, Autorität und Systemkontrolle, KI- und Assistant-spezifische Muster, dialogisch-expressive Sprache, religiös-doctrinale Register sowie somatisch-affektive Intensität.

Die stärkste gemeinsame Lesart lautet: Das Korpus bildet einen mehrdimensionalen Stil- und Funktionsraum, in dem KI-Texte, Autorentexte, institutionelle Texte und dialogische Formen nicht nur nach Herkunft, sondern nach sprachlicher Funktionsweise auseinanderlaufen.

## 1. PCA – Die Grundstruktur des Stilraums

Die Principal Component Analysis reduziert die 159 numerischen Features auf zentrale Achsen des Stilraums. Die ersten 19 Komponenten erklären rund 40,9 % der Varianz. Die Parallel Analysis legt nahe, dass der Korpus nicht eindimensional strukturiert ist.

Inhaltlich zeigen die PCA-Loadings mehrere wiederkehrende Dimensionen: semantische Breite und formale Verdichtung, Autoritäts- und Systemkontrollsemantik, bürokratisch-juridische Form, Assistant-spezifische Dysfunktionsmuster sowie körperlich-affektive und expressive Register.

## 2. Cluster – Emergente Texttypen

Die gewählte 7-Cluster-Lösung stellt derzeit die beste interpretierbare Arbeitslösung dar (auch wenn Silhouette und Gap Statistic zunächst k = 2 favorisierten). Die Cluster bilden keine reinen Metadatengruppen, sondern eher Registerräume:

| Cluster | Deutung |
|--------:|---------|
| 1 | formal-administrative Modell- und Instruktionssprache |
| 2 | sakral-doctrinales Ausreißercluster |
| 3 | Chain-of-Thought Macht- und Autoritätscluster |
| 4 | dialogisch-expressive Interaktionssprache |
| 5 | screenplay- und performative Dialogsprache |
| 6 | literarisch-theoretische Autorensprache |
| 7 | modell-dominante Macht-, Refusal- und Autoritätssprache |

## 3. MANOVA und Canonical Discriminant Analysis

Sowohl MANOVA als auch CDA zeigen starke, strukturelle Gruppenunterschiede. Die wichtigsten rückprojizierten Beitragsbereiche liegen in formaler Verdichtung, Autorität/Systemkontrolle, Registerdissonanz, semantischer Breite und somatisch-affektiver Intensität.

## 4. EFA/SEM – Latente Registerdimensionen

Das derzeit beste sparsame Modell ist das **Strict-5F-Modell** mit folgenden interpretierbaren Faktoren:

- `semantic_somatic_intensity`
- `assistant_collapse_servility`
- `authority_system_control`
- `lexical_syntactic_compression`
- `religious_doctrinal_discourse`

Die Fit-Werte liegen im akzeptablen Bereich für explorative Textdaten.

## 5. LDA – Klassifikatorische Bestätigung und Differenzierung

Ergänzend zur explorativen Strukturanalyse wurde eine MILO-LDA als klassifikatorischer Anschluss durchgeführt. Es wurden zwei Modelle trainiert:

- **Binaere LDA** (`human` vs. `ki`)
- **5-Gruppen-LDA** (`human`, `ki_generic`, `ki_cot`, `ki_personalized`, `extra`)

Die **binaere LDA** ist sehr stark (AUC = 0.987). Die Cross-Validation zeigt eine hohe Trefferquote für KI-Texte (96,7 %), während menschliche Texte etwas häufiger in den KI-Bereich fallen (13,5 %). Dies deutet darauf hin, dass bestimmte menschliche Register formal durchaus KI-nahe Signale aufweisen können.

Die **5-Gruppen-LDA** ist insgesamt weicher. Während `human` und `ki_generic` relativ klar trennbar sind, zeigen `ki_cot` und `ki_personalized` mehr Überlappung mit `ki_generic`. Besonders `ki_cot` wird häufig als generische KI klassifiziert. Die Klasse `extra` ist inhaltlich heterogen und sollte nicht überinterpretiert werden.

Die Achseninterpretation der LDA bestätigt und ergänzt die bisherigen Befunde:
- Die starke binäre Trennachse (LD1) wird vor allem durch formale/strukturelle Verdichtung auf der KI-Seite und semantische Breite plus expressives Rauschen auf der menschlichen Seite getragen.
- Innerhalb des KI-Raums ergeben sich weitere, wenn auch schwächere Differenzierungen (z. B. LD3 trennt `ki_cot` deutlicher ab).

Zusätzlich wurde ein **Forensic Audit Layer** implementiert, der Fälle markiert, in denen die LDA einen Text als menschlich einstuft, aber zusätzliche Signale auf mögliche Mimikry oder Grenzlagen hinweisen.

**Zusammenfassung der LDA:**  
Es existiert eine robuste formale Mensch/KI-Achse. Diese ist jedoch nicht identisch mit den Clustern. Die feinere Typologie innerhalb der KI-Texte (CoT, personalisiert, generisch) ist vorhanden, aber gradueller und poröser als die binäre Trennung.

## 6. Gemeinsame Interpretation

Über PCA, Cluster, CDA, SEM und LDA hinweg stabilisieren sich mehrere große Bedeutungslinien:

- Formale und lexikalische Verdichtung
- Autorität und Systemkontrolle
- KI- und Assistant-spezifische Muster (Servilität, Kollaps, Rekursion)
- Dialogisch-expressive und performative Sprache
- Religiös-doctrinale Register
- Somatisch-affektive Intensität

Diese Dimensionen erscheinen konsistent über verschiedene Methoden und sprechen für robuste Strukturmerkmale des Korpus.

## 7. Ergebnisthese

> KI-, Autoren-, institutionelle und Online-Texte unterscheiden sich entlang wiederkehrender Registerdimensionen. Diese betreffen vor allem Autorität, Formalität, Selbst- und Assistant-Positionierung, Expressivität, religiös-doctrinale Form und somatisch-affektive Intensität.

KI-Texte bilden dabei **keine homogene Klasse**. Generische, personalisierte und CoT-basierte Ausgaben bewegen sich unterschiedlich innerhalb dieses Registerraums. Besonders CoT-Macht- und Autoritätsmuster bilden einen eigenen, interpretierbar stabilen Teilraum.

## 8. Nächste Schritte

Die bisherigen Analysen (PCA, Cluster, CDA, SEM und LDA) haben ein relativ stabiles Bild der Registerstruktur ergeben. Als nächste sinnvolle Schritte bieten sich an:

- Vertiefung der Clusterprofile durch qualitative Textbeispiele
- Weitere Analyse der forensischen Audit-Schicht (Mimikry-Erkennung)
- Prüfung, inwieweit die identifizierten Registerdimensionen in anderen Korpora replizierbar sind
- Übergang in eine stärker confirmatory Phase mit klar definierten Hypothesen