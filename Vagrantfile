VAGRANTFILE_API_VERSION = "2"

Vagrant.require_version ">= 1.7.0"

PROJECT_ROOT = File.expand_path(Dir.pwd + "/../../..")

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "parallels/boot2docker"
  config.vm.synced_folder PROJECT_ROOT, PROJECT_ROOT, create: true, type: "nfs", mount_options: ["nolock", "vers=3", "udp", "actimeo=1"], id: "nfs-sync", nfs_export: false
  config.vm.provision "shell", inline: "sleep 4;sudo cp -rf /var/lib/boot2docker/tls " + PROJECT_ROOT + "/"
  config.vm.provision "shell", inline: "syslogd -R 10.0.3.2", run: "always"
end