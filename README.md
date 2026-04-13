### **Projet: Analysez des images médicales avec des méthodes semi-supervisées**

 **Contexte**  
- 1500 images IRM cérébrales (≈1400 non labellisées, ≈100 labellisées)
- 2 classes labellisées : `normal` vs `cancer`

**Objectifs**
1) Explorer les images + contrôle qualité (doublons / quasi-doublons)
2) Extraire des embeddings (features) via un modèle pré-entraîné (ResNet18)
3) Clustering (KMeans + GMM), évaluation via ARI, création de pseudo-labels
4) Semi-supervisé : comparer
- Supervisé-only (train sur labels experts)
- "Faiblements" labellisées → "Fortement" labellisées (pré-entraînement sur pseudo-labels puis fine-tuning sur labels experts)

**Important**
- On garde **séparé** : (A) labels experts vs (B) pseudo-labels.
- On évite la fuite train/test : doublons exacts + quasi-doublons (group split).

