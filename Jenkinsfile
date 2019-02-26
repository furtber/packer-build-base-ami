node {
	stage("startup") {
		//Remove later.... sho that Jenkinsfile works
		echo "start build"
		env.PATH = "/usr/local/bin/:${env.PATH}"
		env.TF_LOG = "INFO" //TRACE, DEBUG, INFO, WARN or ERROR 
		env.AWS_DEFAULT_REGION = "eu-west-1"

                //AWS account print
                //sh "aws iam list-account-aliases --query 'AccountAliases[]' --output text"
	
                //Packer version print
                sh "packer --version"

		//Ansible version print
		sh "ansible --version"
	}
	stage("bake") {
		//Run packer to build RHEL base AMI 
		sh "packer build packerfiles/rhel_base_ami.json"
	}
}
