# terraformex
##################################Code Terraform##########################################################
provider "github" {
  token = "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"
}

variable "nomrepertoire" {
  description = "Nomrepository"
  type        = string
}

resource "github_repository" "mon_repertoire" {
  name        = var.nom_du_repertoire
  description = "créé via terraform"
  private     = true
}
###################################Code pyhton####################################################
import subprocess
import sys
nomrepertoire = sys.argv[1]
subprocess.run(["terraform", "init"])
subprocess.run(["terraform", "apply", "-auto-approve", f"-var=nom_du_repo={nomrepertoire}"])
#################################################REMARQUES#############################################################"

Bonne exercice sur la pratique terraform ainsi que sur la manipulation de Pyhton.

Merci à vous.

