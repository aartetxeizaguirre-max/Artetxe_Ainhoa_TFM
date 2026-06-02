# Análisis Genómico de la Progresión Metastásica en Melanoma (TCGA-SKCM)

Este repositorio contiene los scripts en R, *pipelines* bioinformáticos y la estructura de resultados asociados al Trabajo de Fin de Máster titulado: **"Identificación de Firmas Genómicas Asociadas a la Progresión Metastásica en Melanoma a través de la cohorte TCGA-SKCM"**.

*   **Autora:** Ainhoa Artetxe Izaguirre.
*   **Institución:** Universidad Internacional de La Rioja (UNIR) - Máster Universitario en Bioinformática.
*   **Director:** Jesus Miguel Perez Gomez.

---

## 🔬 Resumen del Proyecto Académico (TFM)

El melanoma cutáneo presenta una alta incidencia global y una elevada tasa de mortalidad cuando evoluciona a cáncer metastásico. Este trabajo tiene como objetivo principal caracterizar las firmas genómicas que difieren entre el melanoma cutáneo primario y sus metástasis, evaluando su importancia como posibles biomarcadores clínicos. Para ello, se emplea un enfoque bioinformático integrador sobre los datos multiómicos de secuenciación de alto rendimiento (NGS) de la cohorte TCGA-SKCM (Atlas Pan-Cáncer 2018).

### Hallazgos Biológicos Principales:
*   **Carga Mutacional Tumoral (TMB):** Se confirma un incremento significativo de la TMB en la etapa metastásica (mediana de 495 variantes frente a las 314 del melanoma primario). Esto respalda su utilidad como biomarcador predictivo de inestabilidad y respuesta a inmunoterapia.
*   **Firma Etiológica Constante:** La transición nucleotídica C>T domina en ambas fases, lo que ratifica que el daño por radiación ultravioleta (UV) es el evento mutagénico fundacional predominante.
*   **Divergencia en Genes Impulsores (*Drivers*):** Aunque las alteraciones en el gen BRAF se mantienen como el principal evento iniciador, los tumores metastásicos presentan una acumulación significativa y un enriquecimiento diferencial en mutaciones de genes secundarios como NRAS, APC y CDKN2A.
*   **Complejidad en Interacciones Somáticas:** La transición a metástasis viene acompañada de una coevolución somática, evidenciada en redes de interacción génica mucho más complejas (incluyendo eventos de coocurrencia significativa como RASA2-APC o RASA2-NF1) en comparación con las lesiones primarias.
*   **Inestabilidad Cromosómica (CNV):** La progresión metastásica se asocia con una reprogramación estructural masiva, caracterizada por eventos focales concurrentes de amplificación en oncogenes (MITF, MYC, BRAF) y deleciones en supresores tumorales (PTEN, CDKN2A).

---

## 🗂️ Estructura del Repositorio

El directorio de trabajo está diseñado para asegurar la reproducibilidad metodológica del estudio, separando claramente el código fuente de los *outputs* genéricos y específicos de cada cohorte.

```text
📦 TFM-Melanoma-TCGA
 ┣ 📂 scripts
 ┃ ┣ 📜 Fase1_Adquisición_curaciónDatos.Rmd           # Descarga API, limpieza clínica y filtrado MAF
 ┃ ┗ 📜 Fase2_Análisis_Cuantitativo_Estadístico.Rmd   # Análisis de TMB, firmas y CNV
 ┣ 📂 output_skcm_tcga                                # Directorio principal autogenerado
 ┃ ┣ 📂 primary                                       # Datos y visualizaciones: Cohorte Primaria
 ┃ ┃ ┣ 📜 mutations_primary.zip                       # Se sube comprimido por problemas de espacio
 ┃ ┃ ┣ 📜 oncoprint_primary.png
 ┃ ┃ ┗ 📜 somatic_interactions_primary.tsv
 ┃ ┃ ┗ 📜 somatic_interactions_primary.png
 ┃ ┃ ┗ 📜 Resumen_MAF_Primary_noFLAG.png
 ┃ ┣ 📂 metastatic                                    # Datos y visualizaciones: Cohorte Metastásica
 ┃ ┃ ┣ 📜 mutations_metastatic.tsv
 ┃ ┃ ┣ 📜 oncoprint_metastatic.png
 ┃ ┃ ┗ 📜 somatic_interactions_metastatic.tsv
 ┃ ┃ ┗ 📜 somatic_interactions_metastatic.png
 ┃ ┃ ┗ 📜 Resumen_MAF_Metastatic_noFLAG.png
 ┃ ┣ 📂 all_samples                                   # Comparativas y análisis globales
 ┃ ┃ ┣ 📜 clinical_clean.tsv
 ┃ ┃ ┣ 📜 tmb_results.tsv
 ┃ ┃ ┣ 📜 TMB_primary_vs_metastatic.png
 ┃ ┃ ┣ 📜 fisher_primary_vs_metastatic.tsv
 ┃ ┃ ┣ 📜 forestPlot_primary_vs_metastatic.png
 ┃ ┃ ┣ 📜 cnv_focal_summary.tsv
 ┃ ┃ ┗ 📜 cnv_focal_heatmap.png
 ┃ ┗ 📂 tablas                                        # Resultados exportados listos para publicación
 ┃   ┗ 📜 fisher_primary_vs_metastatic.xlsx
 ┃   ┗ 📜 somatic_interactions_primary.xlsx
 ┃   ┗ 📜 somatic_interactions_metastatic.xlsx
 ┗ 📜 README.md
