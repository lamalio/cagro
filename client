<?php
// Connexion à la base de données
$conn = New mysqli_connect('localhost', 'root', '', 'Titres');

// Vérifier la connexion
if ($conn->connect_error) {
    die("Connexion échouée : " . $conn->connect_error);
}

// Récupérer les données du formulaire
$nature = $_POST['nature'];
$numero = $_POST['numero'];
$indice = $_POST['indice'];

// Requête SQL pour vérifier si les données existent dans la base de données
$sql = "SELECT * FROM Titres WHERE nature='$nature' AND num='$numero' AND indice='$indice'";
$result = $conn->query($sql);

// Vérifier si des données existent
if ($result->num_rows > 0) {
    // Afficher les données dans un tableau
    echo "<table border='1'>
            <tr>
                <th>Nature</th>
                <th>Numero</th>
                <th>Indice</th>
                <th>Nb_bornes</th>
                <th>num_borne</th>
                <th>X</th>
                <th>Y</th>
                <th>surf_adop</th>
            </tr>";

    while($row = $result->fetch_assoc()) {
        echo "<tr>
                <td>".$row['nature']."</td>
                <td>".$row['num']."</td>
                <td>".$row['indice']."</td>
                <td>".$row['Nb_borne']."</td>
                <td>".$row['num_borne']."</td>
                <td>".$row['X']."</td>
                <td>".$row['Y']."</td>
                <td>".$row['surf_adop']."</td>
              </tr>";
    }

    echo "</table>";

    // Afficher le formulaire suivant
    echo "<h2>Formulaire suivant :</h2>";
    echo "<form action='suivant.php' method='post'>
            <!-- Ajoutez ici les champs pour le formulaire suivant -->
          </form>";
} else {
    echo "Aucun propriétaire avec ces données";
}

$conn->close();
?>
