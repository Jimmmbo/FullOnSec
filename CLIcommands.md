### SSH tunnel from VPS to localhost
- `ssh -L 9200:localhost:9200 name@Virt.Ual.Ser.Ver`

### Make ed25519 keypair
- `ssh-keygen -t ed25519`
- `-a` + `number` can be added for brute force resistance. For instance `ssh-keygen -a 100 -t ed25519`

### Bash oneliner to check all ssh keys that start with id_*
- ` for key in ~/.ssh/id_*; do ssh-keygen -l -f "${key}"; done | uniq`
