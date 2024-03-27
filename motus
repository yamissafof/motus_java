package Projet;

import java.util.HashSet;

public class Motus {
    public static void main(String[] args) {
        String Mot, Prop;
        int L, LBis;
        String Tab[], TabMot[];

        Mot = Saisie.lire_String("Quel est le mot à trouver : ");
        L = Mot.length();

        while (L <= 3) {
            Mot = Saisie.lire_String("Erreur de saisie, le mot doit avoir plus de 3 lettres. Recommencez : ");
            L = Mot.length();
        }

        Tab = new String[L];
        TabMot = new String[L];

        for (int I = 0; I < L; I++) {
            Tab[I] = Mot.substring(I, I + 1);
        }

        int tentatives = 0;
        final int maxTentatives = 5; // Limite le nombre d'essais

        while (tentatives < maxTentatives) {
            Prop = Saisie.lire_String("Saisissez votre proposition ou SOL pour avoir la solution : ");
            LBis = Prop.length();

            while (!Prop.equals("SOL") && LBis != L) {
                Prop = Saisie.lire_String("Erreur de saisie, la proposition doit avoir la même longueur que le mot à trouver. Recommencez : ");
                LBis = Prop.length();
            }

            if (Prop.equals("SOL")) {
                System.out.println("La solution est : " + Mot);
                break;
            } else {
                int bienPlaces = 0;
                int malPlaces = 0;

                HashSet<Character> dejaVu = new HashSet<>();

                for (int i = 0; i < L; i++) {
                    char lettreProposee = Prop.charAt(i);
                    char lettreAttendue = Mot.charAt(i);

                    if (lettreProposee == lettreAttendue) {
                        bienPlaces++;
                    } else if (Mot.indexOf(lettreProposee) != -1 && !dejaVu.contains(lettreProposee)) {
                        malPlaces++;
                        dejaVu.add(lettreProposee);
                    }
                }

                if (bienPlaces == L) {
                    System.out.println("Bravo, vous avez trouvé le mot qui était : " + Mot);
                    break;
                } else {
                    System.out.println("Bien placées : " + bienPlaces + ", Mal placées : " + malPlaces);
                    tentatives++;
                }
            }
        }

        if (tentatives == maxTentatives) {
            System.out.println("Désolé, vous avez dépassé le nombre maximal d'essais. Le mot à trouver était : " + Mot);
        }
    }
}
