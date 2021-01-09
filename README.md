# Thesis-Charts

How to guide to Helm Charts.

https://helm.sh/docs/topics/charts/  

# Parameters in the values.yaml  

`statefulset.enabled`: Currently set to false. **To be built out**  

`deploymentStrategy`: Uncomment and change as needed **Not currently implemented**  

`rstudio`: Specify information about the rstudio pod's deployment. Includes:  
  `podName`: Change as needed  
  `imageRepository`: Defaults to the rocker docker hub image. **Need to test with custom image**
  `imageTag`: Specific image tag to use (don't include in the `imageRepository` value.
  `imagePullPolicy`: Change as needed **Not tested**
  `env`: These are the two required for the rocker/rstudio image. **Need to change impentation of tese values in the deployment template to allow various number of environmental variable key-value pairs.**  
    `firstEnvName`: Required by the rocker image. Don't change. **Username is rstudio**  
	`firstEnvValue`: Change as needed.
	`secondEnvName`: Don't change.  
	`secondEnvValue`: Options "TRUE" or "FALSE"  
  `resources`: Provide resources as required. **Need to test and build out options**  
  `service`: These should not change but need to include in the output what the actual address and port are.  
`imagePullSecrets`: Not used right now **To be built out**  
`nameOverride`: Change as needed.  
`fullnameOverride`: Change as needed.
`serviceAccount`: **Need to test if this is needed and what it provides**  
  `create`: true/false  
  `annotations`: **To be built out**  
  `name`: **To be built out**  
`podAnnotations`: **To be built out, waht is this for?**  
`podSecurityContext`: **To be built out**  
`securityContext`: **To be built out**  
`ingress`: Not sure what this does for us. **To be built out**  
  `enabled`: true/false  
  `annotations`: Not sure  
  `hosts`: Not sure 
  `tls`: Not sure  
`autoscaling`: Rules to determine autoscaling. Not sure about loadbalancing and applicability for this. **To be built out**  
  `enabled`: true/false  
  `minReplicas`: 1  
  `maxReplicas`: 100  
  `targetCPUUtilizationPercentage`: 80  
`nodeSelector`: **To be built out**  
`tolerations`: **To be built out**  
`affinity`: **To be built out**


# Deploy the helm chart 

Navigate to the root folder of this project. Execute the following command to install the chart:  

```{bash}

helm install rstudio ./firstChart/

```  

