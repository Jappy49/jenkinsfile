pipeline {
	agent {  label 'linux agent' }
	stages {
		stage('---clean----'){
			tools {
				maven 'maven_3.9.5'
			}
			steps {
				sh 'mvn --version'
				sh "mvn clean"
			}
		}
		stage('---test---') {
			tools {
				maven 'maven_3.9.4'
			}
			steps {
				sh 'mvn --version'
				sh "mvn test"
			}
		}
		stage('---package---'){
			tools {
				maven 'maven_3.9.0'
			}
			
			steps {
				sh 'mvn --version'
				sh "mvn package"
			}
		}
	}
	stage('----deploy-----')
	{
		
	steps {
		sh 'scp /home/ec2-user/linuxagent/workspace/*.war -i -----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAzXaGMJbOuUpjo1tk/MkVwt0hK4XbcjMIejLdkD0sgzVuWRdd
cA1zxf+3CPt3tdT3NiBaBk3l5sDFMA+SUq1kUuOuFWY4drxtIo9ZWkSvTqLgSLzF
TH7dmAG+N57G1gF/qmOPEFmEycJz6rKG4y3n/+Nc+RTw1tJ3jT+GAtY9Jeok9kig
+u7RMSXxwrZhdNtnEwIJi/wCrND9zb5Z5Nf/QcNAD2BWogvWr3vF5DonjikFbYzc
g4CnWiobEdgOC2mE3y/RI4iMdgaoB+opxqo+eMhT85kAdYv665yikrzTqiw4p32f
w7iLZdqQe+UHdT2V+uiKh34KvzTFfVwRwbtoiwIDAQABAoIBABrkgpflhVVXWUdO
dR9pKoIA85CAysJdz6Q++CUi/KqH2dOrbT13ZUnrOIficj7Iizr4bRAaLhdP7/9k
amCL9W+sAWMnqAhSjW5SmP1ptBB03SpoGuLyUArPX5hkHd5w/8bLlTQso2bNHuL/
Twx5O76QgeDQTt2vWpqQT/gbFpHZobC5fCw0KtpLbJBtRWFkIhs/uB45KyCboPbW
oOeaWnjm5gShuBHBqJsD2U6Jm8Hm6Gx7X+NZBy7/1URj7my7FI8Gx8ZwjW57TVh6
KAQwuWY/Bz1hMU0a7xuGSf/VAPfrbFuhhXDa3Zdj7JJ6VVi3m+T76r3PCrNnbUn7
42fSUsECgYEA8hvHFLmlbLE2GGDeq+BYrxAMxb7pcVZ/JZAnS0uh1B87HtAjXzYQ
sdfmIe/pIVWiS5+xUVSaMVZb8UQekfi9JsL5ZHWrAfUqjVJx8w09xZpBMrzVWZL8
OpFf/+hcDHOwHPx2h3WfYV0rHBklEU635wAXEoWhbZTrdDwkAm2O+HECgYEA2UB6
Hq2Mv5G3LhVT/A0nWiQ1kTeyIcmsWASKeHoyOhQ5u42s62FsqKv/wV5p57wtXSCm
eGt0rj1fnSxLKF8HSwHKbQA5drdF4Di8x7Hwz84Z221OSSqoN4juOFu9VGf0QDmf
+4ZBUhOfZljf1wWbF9VHxxn7ZcMF6NGv/YzxzrsCgYEArJRYaNGctcnsgZwrneEh
1khekmbwCLZbk+8Z03ZqOMa6YdCEJk5nwB3iEbbuO7DLK5T91Le14g1pJKYmFG92
hbbeB1pJN/AHEQ3/4/1AVycJ6pzoiB1aZnVSNRzw4H9mvoLICu8xWToMjM7vuVKf
jK5nw/A1jeNlo0lrcb+e9kECgYBjZhW5rYwFJkVaZ1W6r8X+fyynGYV94gjhaIp2
XupWGmTjxAmG1FdjwPZOYcUwyq8yubqQxBFpmxkBD3//o6LxlYspXf3srCPjV/I/
p9FXMqQv+g3kegjnB9Z+oLK6SKm/LN5etWlzhRjcOfOILL9uIx4pIWEdiSJOCIpu
Bqun+wKBgQDpewke+HIvvUrDPjPWg4a6T05DLORNiv1HBomAJ1HTELxve/nOORYn
o9mSUOpIHdUPiRJctWyTbYJ7/DiV7ts6FgTZLZsuO4+o13SYBaErdPLDgHtE9b4W
vLjs1jTead9eCXKNtgT1QFA9ZhHeOajT6sABmklUiD1JuCPr+f8xLw==
-----END RSA PRIVATE KEY----- ec2-user@52.64.89.226 /home/ec2-user /home/ec2-user/apache-tomcat-9.0.83/webapps   '
	}
	}
	
		
	post {
		success {
			echo 'job was built successfully'
		}
		failure {
			echo 'job was not build..it was failed'
		}
	}
}
