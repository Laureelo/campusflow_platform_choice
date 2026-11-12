# Fiche comparative Android / iOS

Cas étudié : une application étudiante (suivi des échéances) utilisée en Afrique francophone, par des étudiants de master et de licence.

Chiffre de départ, tiré du cours (séance 1, diapo 10) : en Afrique, environ 83 % des pages vues web mobiles viennent d'Android et 15,8 % d'iOS (StatCounter, début 2026). C'est une mesure d'usage web, pas un nombre d'appareils, mais l'écart est assez grand pour orienter les choix.

| # | Critère | Android | iOS | Ce qui change pour notre cas |
|---|---|---|---|---|
| 1 | Philosophie | Open source (AOSP), plusieurs constructeurs | Fermé, matériel et logiciel d'un seul fournisseur | Android existe à tous les prix, donc il est présent chez les étudiants. Un iPhone coûte cher par rapport à un budget étudiant. |
| 2 | Architecture | Noyau Linux, ART | Darwin / XNU, Cocoa Touch | Pas d'effet direct sur l'utilisateur. Sur un téléphone avec peu de mémoire, il faut une application légère. |
| 3 | Environnement de développement | Android Studio sur Windows, macOS, Linux | Xcode, macOS uniquement | Nous travaillons sous Windows. On peut tout tester sur Android, mais pas compiler pour iOS sans Mac. |
| 4 | Langage | Kotlin (Java), Jetpack Compose | Swift, SwiftUI / UIKit | Deux langages à apprendre en natif. Avec Flutter on n'en apprend qu'un, Dart. |
| 5 | Modèle d'application | Activités, services, paquet APK / AAB | Scènes et vues, paquet IPA | Un APK peut être envoyé directement (lien, clé USB, messagerie). C'est pratique quand tout le monde n'a pas de carte bancaire pour un magasin d'applications. |
| 6 | Cycle de vie | onCreate, onResume, onPause, onDestroy | Active, inactive, arrière-plan, suspendue | Le système tue souvent les applications en arrière-plan sur les petits téléphones. Il faut sauvegarder l'état et le restaurer proprement. |
| 7 | Matériel | Nombreux constructeurs, nombreuses gammes | Quelques modèles | Il faut penser aux petits écrans, aux 2 Go de RAM et aux processeurs modestes. |
| 8 | Permissions | Demandées à l'exécution, une par une | Demandées à l'exécution avec un texte d'explication | Les rappels d'échéance demandent la permission de notifications. Il faut expliquer pourquoi, sinon l'étudiant refuse. |
| 9 | Stockage | Bac à sable, stockage cloisonné, Keystore | Bac à sable, Keychain | La connexion est parfois coupée. Les échéances doivent rester lisibles hors ligne, donc stockées en local. |
| 10 | Sécurité | Signature, Play Protect, bac à sable | Signature, revue Apple, bac à sable | Si l'APK circule hors magasin, un étudiant peut installer une fausse version. Il faut signer l'application et expliquer d'où la télécharger. |
| 11 | Distribution | Google Play, autres magasins, installation directe | App Store, ouverture variable selon la région | Google Play coûte 25 $ une seule fois, l'App Store 99 $ par an. Le paiement en ligne n'est pas évident partout, donc la distribution directe compte. |
| 12 | Fragmentation | Beaucoup de versions d'OS, de constructeurs, de tailles d'écran | Faible, les mises à jour sont adoptées vite | Beaucoup de téléphones restent sur des versions anciennes. Il faut viser une version minimale basse. |
| 13 | Mises à jour | Selon le constructeur et l'opérateur | Directes par Apple | Un téléphone peut ne jamais recevoir la dernière version d'Android. L'application ne peut pas compter sur les nouvelles API. |
| 14 | Contraintes pour le développeur | Tests sur de nombreux appareils | Mac obligatoire, revue App Store | Android demande beaucoup de tests, iOS demande du matériel et une validation. Avec nos moyens, Android passe en premier. |

## Ce qui change le plus

Trois critères pèsent plus que les autres dans ce contexte : le prix du matériel (1 et 7), l'absence de Mac (3 et 14) et la distribution (5 et 11). Ils poussent vers Android en premier, et vers un seul code partagé pour ne pas payer deux fois le développement.
