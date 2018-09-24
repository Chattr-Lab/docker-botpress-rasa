# Botpress and Rasa, together at last

This is a Docker-ized application using Botpress and Rasa together. Right now it doesn't do much, but some day it might.

## To run

    docker-compose up

Visit the botpress app at http://localhost:3000

## To create new NLU data

You can try creating intents and entities inside Botpress. I haven't had much luck with that yet. You might be better off editing `rasa/data/nlu.md` and manually training.

You can do the training with:

    docker-compose run rasa run python -m rasa_nlu.train -c /app/config.yml -d /app/data --project default -o projects

I'm still working on how to get the botpress instance to use the "default" project, but I'm sure there's a way. Probably editing something inside `botpress/config/nlu.json`.
