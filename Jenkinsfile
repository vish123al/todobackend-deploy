node {
  checkout scm

  stage 'Deploy application release'
  writeFile file: 'extras.json'
  withEnv(["VAULT_PASSWORD=${VAULT_PASSWORD}"]) {
    sh 'ansible-playbook site.yml --vault-password-file vault.py -e "@extras.json"'
  }
}
