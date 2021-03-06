## These steps are used to create a Linux VM in OCI as an alternative to running VirtualBox Linux locally (laptop/mac).
## This VM will have the most common CLI's pre-installed - such as oci, kubectl, helm, git suitable to be used with OKE

### High Level Steps
* First create a OKE cluster using Quick Create.
* Create a public subnet using CIDR different from existing subnets - Example: CIDR 10.0.20.0/24 with default route and security in the same OKE VCN
* Create a compute instance using VM.Standard.E2.1

**Note: ssh keys are provided as a sample but generate or re-use your own keys for security**

  * Choose mykey.pub from [mykey.zip](https://github.com/venkat50/hands-on-lab/raw/master/OCI/mykeys.zip)
                       OR
  * Paste key: 
  `ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDT53WIGqHj+7FXJiRRCmrxCmE+qJvjrJSASinhs8/aEEm4XhsSDy67gXSovrkjSq//kisET6wmOymKCEF2zQGxyZY/rBCLOc/of1sm2Yoo5S1bNvKJQbgjN9LPz0EXOs3qGThUKQKsthQOeWgZGoUiaLplskGBVmXQ+3WT8vtNZxJ9fbCp89fRGyUzF9fSCclpp7eAqirSOhgAoK8D6S1138kxxTwpc32A4FRqrTaqaWlioCjzxRFTnygSnOEgPv2Go7CPSsFghm2XYVyAtsftIEFyphVSJ66CbfjRw+L9b6v8/fRzA0UBZwtLxECO6WSXbGNKhTXJ3T0CKXXRgzCH imported-openssh-key`
  * Use Advanced options and paste content of [cloud-init.txt](https://github.com/venkat50/hands-on-lab/raw/master/OCI/cloud-init.txt)
  <!-- * [TBD] `bash -c "$(curl -L https://raw.githubusercontent.com/venkat50/hands-on-lab/master/OCI/hol-setup.sh)" ` -->
  * Ensure you have selected newly created subnet
* Use ssh or putty to connect using pblic IP after VM is in running status
  * Windows users use mykey.ppk and login as user opc
  * Mac or Linux use `ssh -i mykey opc@<IP Address>`
  
## Detailed Steps:

### Task 1: Create Public Subnet

[x] Select VCN        
    ![subnet1](../images/Subnet1.png)
    
[x] Specify CIDR 10.0.20.0/24
    ![subnet2](../images/Subnet2.png)   
   
### Task 2: Create Compute instance

[x] Select Shape VM Standard E2.1
    ![shape](../images/Instance3.png)

[x] Select mykey public key
    ![pubkey](../images/Instance4.png)

[x] Advanced Options: Paste cloud-init script 
    ![cloud_init](../images/Instance5.png)


# Link to [Hands on Lab](https://github.com/nagypeter/weblogic-operator-tutorial/blob/master/tutorials/domain-home-in-image.md)

# Continue from [here](https://github.com/nagypeter/weblogic-operator-tutorial/blob/master/tutorials/setup.oke.md#prepare-oci-cli-to-download-kubernetes-configuration-file)


