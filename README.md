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

#########################################################Exercice7###################################################
terraform {
  required_providers {
    vultr = {
      source  = "vultr/vultr"
      version = "2.17.1" 
    }
  }
}
provider "vultr" {
  api_key = "SILLVA2A6J3F6S4SKKSNXAPFNZFMWNFF2MRA"
}
resource "vultr_instance" "suleiman" {
  region  = "fra"
  plan    = "vc2-1c-1gb"
  os_id   = "387"
 user_data = <<-EOF
              #!/bin/bash
              sudo apt-get update
              sudo apt-get install -y docker.io
              sudo systemctl start docker
              sudo systemctl enable docker
              EOF
  }


