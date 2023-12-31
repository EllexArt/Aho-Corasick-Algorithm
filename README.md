# Aho-Corasick-Algorithm

L'ensemble des fonctions suivantes s'exécutent après l'exécution de la commande make, qui permet de compiler et rendre exécutable l'ensemble du projet.


Comment utiliser le générateur de texte ? 

Le générateur de texte s'utilise par l'usage d'une commande qui est :
./genere-texte <taille du texte à générer> <taille de l'alphabet sur lequel produire le texte>
Un texte sera alors généré aléatoirement et écrit sur la sortie.


Comment utiliser le générateur de mots ?

Le générateur de mots s'utilise par l'usage d'une commande qui est :
./genere-mots <nombre de mots à générer> <taille minimale des mots à générer> <taille maximale des mots à générer> <taille de l'alphabet sur lequel produire les mots>
Une liste de mots sera alors générée aléatoirement et écrit sur la sortie, séparés par un retour à la ligne.


Comment utiliser le Trie ?

Pour utiliser les tries, les fonctions sont définies dans le fichier trie.h et implémentées dans deux fichiers c de manière distincte : on retrouvera ainsi dans le fichier trie_hash.c le trie par table de hachage et dans trie_matrix.c le trie par matrice de transition.
Pour utiliser l'une ou l'autre version, il faudra utiliser le fichier c correspondant.
Les fonctions sont déclarées dans le fichier trie.h.

Il est ainsi possible de créer un trie avec la fonction createTrie(int maxNode). Cette fonction prend en paramètre un entier désignant le nombre maximal de noeuds que le trie pourra comporter.

Il existe aussi la fonction insertInTrie(Trie trie, unsigned char *word). Cette fonction prend en paramètre un trie et un mot, ce mot sera inséré dans le trie s'il reste de la place.

On peut également retrouver la fonction isInTrie(Trie trie, unsigned char *word) qui donne la possibilité de rechercher si le mot spécifié est présent dans le trie.

La fonction printTrie(Trie trie) permet d'afficher sur la sortie standard le contenu du trie.

La fonction freeTrie(Trie trie) permet quant à elle de libérer les ressources allouées par le trie.

Il est également possible de récupérer le noeud d'arrivée d'une transition dans le trie à partir de son noeud de départ et la lettre de transition avec la fonction getNodeFromCharacter(Trie trie, int beginNode, unsigned char letter).

Pour vérifier si un trie ne contient plus de place disponible, il est possible d'appeler la fonction isTrieFull(Trie trie).

De même, on peut vérifier la présence d'un noeud dans le trie avec la fonction isNodeInTrie(Trie trie, int node).

On peut également rendre l'un des noeuds du trie final avec la fonction setNodeFinal(Trie trie, int node), ou encore vérifier si le noeud est final avec isNodeFinal(Trie trie, int node).

Enfin il est possible de récupérer le dernier noeud ajouté au trie avec la fonction getLastNode(Trie trie).



Comment utiliser l'algorithme Aho-Corasick ?

L'algorithme d'Aho-Corasick est utilisable par l'usage d'une commande qui est (selon le type de trie choisi) :
./ac-matrice <texte contenant la liste de mots> <texte contenant le texte>
ou
./ac-hachage <texte contenant la liste de mots> <texte contenant le texte>

Il est également possible d'accéder aux fonctions de l'algorithme tel que :
- initAhoCorasick(unsigned char **wordList, int numberOfWord, int *sup, int *numberOfOccurrencies) qui renvoie le trie contenant les mots donnés et effectue le pré-traitement de l'algorithme
- complete(Trie trie, int *sup, , int *numberOfOccurrencies) qui ajoute les états d'adjacence au trie
- ahoCorasick(unsigned char **wordList, int numberOfWord, char *text, int textSize) qui exécute l'algorithme d'Aho-Corasick.


Comment utiliser le fichier de statistiques python (stat.py) ?

Tout d'abord, il faut s'assurer d'avoir pip d'installé, ou du moins le module matplotlib.
Le cas échéant, il faut exécuter les commandes suivantes :
sudo apt-install python3-pip
pip install matplotlib

Il faut également avoir exécuté préalablement les scripts :
./genereTexteEtMots.sh
./executeAlgo.sh

Une fois le module installé et les autres scripts exécutés, il suffit d'exécuter la commande python3 ./stat.py et s'afficheront alors les graphiques d'analyse des données calculées précédemment.

