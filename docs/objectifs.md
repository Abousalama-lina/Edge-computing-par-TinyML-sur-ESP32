---
layout: default
nav_order: 2
title:  Edge-computing-par-TinyML-sur-ESP32
---

## Contexte

Projet réalisé dans le cadre d’un stage de 2 mois à UniLaSalle Amiens, sur un sujet proposé et encadré par Jérôme Gorin, avec le matériel du MakerSpace. C’est la première étape d’un programme en trois cas d’usage (objets, expressions faciales, anonymisation de données médicales).

## Problème et public cible

Analyser des images par IA sans passer par le cloud (latence, dépendance au réseau, confidentialité), en faisant tenir un modèle dans les limites d’un microcontrôleur ESP32 (mémoire, puissance, vitesse d’inférence).
Les étudiants (guide pédagogique reproductible), puis les acteurs de la santé (anonymisation locale de données médicales).
Fonctionnement autonome et en temps réel sur la carte, sans réseau, avec au moins 80 % de précision, 2 images par seconde et un modèle de 300 Ko au maximum, et des images qui ne quittent jamais l’appareil.

## Cahier des charges

| Fonction                                                           | Critère                                                                       | Niveau attendu                                        | Flexibilité |
|--------------------------------------------------------------------|--------------------------------------------------------------------------------|------------------------------------------------------|-------------|
|FP1 : reconnaître un chien, un chat ou « rien » devant la caméra    |	Précision sur un jeu de test réel (images prises par la caméra de la carte)   |	≥ 80 %                                               	|     F1     |
|FP2 : analyser en temps réel                                        | 	Débit d'inférence (soit ≤ 500 ms par image)                                   |	≥ 2 images par seconde                                 |    F1     |
|FP3 : permettre aux étudiants de reproduire la chaîne               |   Guide pas à pas suivi par un etudiant                                        | Reproduite par un étudiant sans aide                   |	  F1     |
|FC1 : tenir dans la mémoire de la carte                             |  Taille du modèle .tflite                                                      |  ≤ 300 Ko                                              |    F1     |    |FC2 : fonctionner sans réseau                                       |   Image transmises hors de la carte                                            |  0                                                    |    F0     |
|FC3 : protéger les données personnelles                             |  Photos de personnes avec consentement                                         | 100%                                                  |    F0      |

