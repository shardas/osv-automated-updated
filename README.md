# osv-automated - Automated Install of OSV and supporting operators [WIP]

Follow these steps to run:

1. Install AAP Operator (cluster scope)
2. Create AutomationController instance named automationcontroller
3. Follow route (aap namespace -> routes) to newly created automation controller instance
4. Login AAP as admin using credentials in secret automationcontroller-admin-password in namespace aap
5. Subscribe AAP Instance
6. Create ansible-sa service account in aap namespace (oc apply -f ./openshift-resources/openshift-ansible-sa.yaml) (note this gives the cluster admin privileges, if doing this in a non-testing environment, you'll want to limit the scope of this users access)
7. In AAP, create credential with type OpenShift or Kubernetes API Endpoint using the ansible service account token you just created and the cluster API URL (ensure there are no trailing spaces in the API URL)

