VAGRANTFILE_API_VERSION = "2"

Vagrant.require_version ">= 1.6.5"

IMEGA_ROOT = "/usr/local/imega"
DOCKER_CPUS   = 1
DOCKER_MEM    = 1024

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "parallels/boot2docker"
  config.vm.synced_folder "../..", IMEGA_ROOT, create: true, type: "nfs", nfs_export: false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  
  config.vm.provider "parallels" do |v|
    v.cpus = DOCKER_CPUS
    v.memory = DOCKER_MEM
  end
end
