node {
  scmVars = checkout scm
  def ecr = new org.bellhops.ECR()

  ecr.login('airflow', 'us-east-1')
  //Do not push until we've tested this.
  airflow_image = ecr.build('airflow', '.', false) 
  // TODO: Write testing logic 
  echo "Do testing here."
  // End Testing Logic 
  //Separate Push statement - keeps us from pushing containers that don't finish CI 
  ecr.push(airflow_image, scmVars.GIT_COMMIT)
}