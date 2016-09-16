Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-16.04"
  config.vm.define "knowabunga-web"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Conference wifi or corp proxy setting
  config.vm.box_check_update = false

  config.vm.provision "ansible" do |ansible|
    # ansible.verbose = "vvvv"
    ansible.playbook = "playbook.yml"
    ansible.groups = {
      "webservers" => ["knowabunga-web"],
    }

    ansible.host_vars = {
      "smokerunner" => {
        "ansible_connection" => "local",
      }
    }
  end
end
