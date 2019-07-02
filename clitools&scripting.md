### SSH tunnel from VPS to localhost
- `ssh -L 9200:localhost:9200 name@Virt.Ual.Ser.Ver`

### Make ed25519 keypair
- `ssh-keygen -t ed25519`
- `-a` + `number` can be added for brute force resistance. For instance `ssh-keygen -a 100 -t ed25519`

### Bash oneliner to check all ssh keys that start with id_*
- ` for key in ~/.ssh/id_*; do ssh-keygen -l -f "${key}"; done | uniq`

### ssh-add
- make sure ssh agent is running with `eval "$(ssh-agent -s)"`
- then run `ssh-add`

### Bash aliases
- in `.bash_profile` (macOS) or `.bashrc` (Linux) put `alias ls='ls -lahtr' for example 

### (Bash) regex for checking if an IPV4 is presented
 - `if [[ $ip =~ ^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}$ ]]; then`

### Remove Windows carriage return (^M)
- `sed -e 's/\r$//g' input > output`
* Dit moet gerunt worden op een linux omgeving. Unix heeft 'sed' en 'tr' versies van FreeBSD

### Create random password in Linux by using the noise the drivers generate in urandom 
- `head /dev/urandom | tr -dc A-Za-z0-9 | head -c10`
* /dev/urandom kan gebruikt worden voor psuedo-random wachtwoorden. Wil je GPG/SSH keys maken, dan moet je /dev/random gebruiken omdat hier meer entropy aan toegevoegd wordt. /dev/random wacht ook echt op een zeker gehalte van entropy en kan dus blocken als dit niveau niet bereikt is, waar /dev/urandom nooit blocked. 
