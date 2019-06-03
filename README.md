# cours-ELK
Aide sur ELK


# Préparation d'un beat d'analyse. Cette phase ne se fait qu'une seule fois.

```bash
cd /tmp
export GOPATH=/tmp/go
git clone https://github.com/elastic/beats ${GOPATH}/src/github.com/elastic/beats

# Créer votre projet de beat
# !! Attention à mettre un user github
mkdir /tmp/go/github.com/${user}
cd /tmp/go/github.com/${user}

# Préparation de la structure à partir des scripts elastics
python ${GOPATH}/src/github.com/elastic/beats/script/generate.py

```
Vous pouvez maintenant développer votre beat.

# Integration dans votre github
Vous pouvez intégrer cette chaîne dans un projet github du même nom que vous pourrez diffuser.
```bash
# Allez sur le site de github et créez votre projet, avec le bon nom
# Puis greffez votre code sur le github

git remote add origin git@github.com:${user}/${beatname}.git
git push -u origin master

```

# Préparation de la chaîne
```bash
cd ${monBeat}
make setup
```

# Lancement du beats
```bash
make
./${monBeat} -e -d "*"

```
