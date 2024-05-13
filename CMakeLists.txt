cmake_minimum_required(VERSION 3.5)
project(calculator C)

# Ajout du répertoire include et src
add_subdirectory(include)
add_subdirectory(src)

# Inclusion des répertoires d'en-tête
include_directories(include)

# Activation des tests
enable_testing()

# Définition des tests
add_test(t1 src/calculator add 2 3)
add_test(t2 src/calculator sub 3 -2)
add_test(t3 src/calculator mul 5 5)
add_test(t4 src/calculator div 1 5)
add_test(t5 src/calculator square 5) # Nouveau test pour la fonction au carré
