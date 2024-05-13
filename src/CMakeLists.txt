add_subdirectory(lib)
add_executable(calculator main.c)
target_link_libraries(calculator libcmake_minimum_required(VERSION 3.5)
project(calculator C)

# Ajout du répertoire include et src
add_subdirectory(include)
add_subdirectory(src)

# Inclusion des répertoires d'en-tête
include_directories(include)

# Activation des tests
enable_testing()

# Définition des tests en parallèle
add_test(NAME t1 COMMAND src/calculator add 2 3)
add_test(NAME t2 COMMAND src/calculator sub 3 -2)
add_test(NAME t3 COMMAND src/calculator mul 5 5)
add_test(NAME t4 COMMAND src/calculator div 1 5)
add_test(NAME t5 COMMAND src/calculator square 5) # Nouveau test pour la fonction au carré

# Activation de l'exécution des tests en parallèle
set_tests_properties(t1 t2 t3 t4 t5 PROPERTIES PARALLEL_LEVEL 5)
