#!groovy
@Library('roboshop-shared-library-1') _
// responsibility to pass what type of application and component is this to pipeline deicssion

def configMap = [
    application: "nodejsVM",  /* we are creating list of variables */
    component: "catalogue"
]
if( ! env.BRANCH_NAME.equalsIgnoreCase('main') ) { /* if we put ! it works as opposite */
    pipelineDecission.decidepipeline(configMap) /* here we creatinhg pipelineDecission.decidepipeline function and we provide input as configMap */
}
else { /* it is main */
    echo "This is production, deal with CR process"
}
