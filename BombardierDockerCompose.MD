## Launch multiple bombardier docker containers at the same time with docker compose

<ol>
  <li>Copy the content in the code block in a file named 'docker-compose.yml'</li>
  <li>Replace CONNECTIONS with the amount of connections you want to use.</li>
  <li>Replace URL with the url's you want to use.</li>
  <li>Add more containers if you want.</li>
  <li>Run 'docker-compose up' in the folder where docker-compose.yml is (in the terminal/command prompt)</li>
  <li>Alternatively, run 'docker-compose up -d' to run in detached mode, 'docker-compose down' to remove te containers</li>
</ol>

    version: "3"
    services:
      bombardier1:
        image: alpine/bombardier
        command: -c CONNECTIONS -d 3600s -l URL
      bombardier2:
        image: alpine/bombardier
        command: -c CONNECTIONS -d 3600s -l URL
      bombardier3:
        image: alpine/bombardier
        command: -c CONNECTIONS -d 3600s -l URL

More info: https://docs.docker.com/compose/