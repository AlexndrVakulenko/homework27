Vagrant.configure(2) do |config|
     config.vm.define "DynamicWeb" do |vmconfig| 
      vmconfig.vm.box = 'bento/ubuntu-22.04'
      vmconfig.vm.hostname = 'DynamicWeb'

      vmconfig.vm.network "forwarded_port", guest: 8083, host: 8083
      vmconfig.vm.network "forwarded_port", guest: 8081, host: 8081
      vmconfig.vm.network "forwarded_port", guest: 8082, host: 8082
      vmconfig.vm.provider "virtualbox" do |vbx|
       vbx.memory = "2048"
       vbx.cpus = "2"
       vbx.customize ["modifyvm", :id, '--audio', 'none']
      end
     end
    
     config.vm.provision "ansible" do |ansible|
      ansible.playbook = "work_web.yml"
      end
end
