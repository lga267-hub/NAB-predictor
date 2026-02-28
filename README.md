# Predictor Clínico de Inmunogenicidad (NAbs) para Toxina Botulínica A en Espasticidad

Este repositorio contiene un dashboard clínico interactivo diseñado para estimar la probabilidad absoluta de desarrollar anticuerpos neutralizantes (NAbs) secundarios al tratamiento con Toxina Botulínica A (BoNT-A) en pacientes con espasticidad (adultos y pediátricos).

## Base Científica y Modelo Matemático

A diferencia de las calculadoras heurísticas simples, este modelo utiliza una **ecuación de regresión logística continua** calibrada con *Odds Ratios (OR)* extraídos de metaanálisis y consensos internacionales recientes sobre inmunogenicidad neurológica. 

El algoritmo calcula la probabilidad en tiempo real basándose en la carga antigénica y la exposición del sistema inmunológico, ajustando el riesgo base (~1.4% - 1.5% para pacientes crónicos estándar) mediante las siguientes variables:

* **Historial de Exposición:** Escala el riesgo desde pacientes *Naïve* (riesgo virtualmente nulo en la primera exposición) hasta pacientes crónicos (> 2 años) donde la respuesta adaptativa de las células B está latente.
* **Formulación (Carga Proteica):** Discrimina el riesgo según la presencia de proteínas complejas (hemaglutininas). Asigna protección a toxinas purificadas como IncobotulinumtoxinA (INCO), cuyo OR reduce drásticamente el riesgo según la literatura (ausencia de NAbs).
* **Frecuencia de Inyección:** Penaliza severamente (OR elevado) los intervalos de tratamiento inferiores a 12 semanas y las dosis de refuerzo (*boosters* tempranos), identificados como el principal desencadenante de inmunoresistencia.
* **Dosis Continua Exponencial:** A diferencia de la medicina estética, la espasticidad requiere dosis masivas. El modelo ajusta el riesgo de forma continua (aumentando un ~12% el riesgo relativo por cada 100 unidades extra de toxinas con proteínas accesorias).

### Bibliografía de Referencia Principal
* *Fabbri M, et al. (2016).* Neutralizing Antibody and Botulinum Toxin Therapy: A Systematic Review and Meta-analysis. Neurotox Res.
* *Carr WW, et al. (2021).* Immunogenicity of Botulinum Toxin Formulations: Potential Therapeutic Implications. Adv Ther.
* *Hefter H, et al. (2020).* Effective long-term treatment with incobotulinumtoxin (Xeomin) without neutralizing antibody induction: a monocentric, cross-sectional study. J Neurol.

## Cómo usar este Dashboard

1.  Escanea el código QR proporcionado por el autor o visita el enlace web de GitHub Pages de este repositorio.
2.  Introduce el perfil clínico de tu paciente en el formulario (Historial, Toxina, Dosis y Frecuencia).
3.  La calculadora actualizará automáticamente la estimación de riesgo absoluto en pantalla sin necesidad de recargar la página.

> **Aviso Médico / Disclaimer:** > Esta herramienta ha sido desarrollada con fines puramente educativos, académicos y de apoyo a la decisión clínica. No sustituye el juicio clínico del profesional médico ni las pruebas de laboratorio (como el ensayo de hemidiafragma de ratón o ELISA) para confirmar un fallo secundario del tratamiento real.
