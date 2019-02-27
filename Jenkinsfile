node {
	stage("startup") {
		//Remove later.... sho that Jenkinsfile works
		echo "start build"
		env.PATH = "/usr/local/bin/:${env.PATH}"
		env.AWS_DEFAULT_REGION = "eu-west-1"

                //Packer version print
                sh "packer --version"

		//Ansible version print
		sh "ansible --version"
	}
	stage("bake") {

		//Checkout current project .. other can be checked out using git
		checkout scm

		//Run packer to build RHEL base AMI 
		sh "packer build ./packerfiles/rhel_base_ami.json"
	}
}
