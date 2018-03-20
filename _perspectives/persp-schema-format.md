---
title: Understand Format of Perspectives Schema
position: 2
description: Learn about the Perspective Schema Format. 
parameters:
  - name: name
    content: String that specifies the name of the Perspective. The name need not match the name of an existing (active or archived) Perspective.
  - name: include_in_reports
    content: Boolean that specifies whether the Perspective is included in CloudHealth Reports. Specify as `true` (default) or `false`.
  - name: rules
    content: An array of rules (objects) that govern Perspective membership. The ordering of the rules matters. Rules are evaluated in order starting from the first one in the array. This parameter simplifies the process of reordering a Group. Run a read operation to get the schema of a Perspective, change the order in the schema in a text editor, and upload the modified schema to the same Perspective.
  - name: merges
    content: List of merge objects, which can be of type Dynamic Group or Dynamic Group Block. The Dynamic Group merge allows for two Groups to merged and the Dynamic Block Group is to merge two entire blocks of Groups. Each merge specifies a list of source objects and a single target object (Groups or blocks), where the sources are to be merged into the target.
  - name: constants
    content: List of reference objects that refer to Groups, blocks, and assets that are specified in rules. When a schema is retrieved through a GET operation, every Group (dynamic and static) is listed in the this section. Although meant mainly for reference, constants can be modified to change the name of Groups and blocks. The full list of potential constant types is provided below.
content_markdown: |-
  Constant Types can either be `Dynamic Group`, `Static Group`, or an asset type listed below.

  > Expansion types such as `AwsAsset` or `AzureTaggableAsset` are not included.
  {:.info}

  - AwsAccount
  - AwsAvailabilityZone
  - AwsGroup
  - AwsImage
  - AwsInstance
  - AwsInstanceReservation
  - AwsInstanceStatus
  - AwsInstanceType
  - AwsRdsInstance
  - AwsRegion
  - AwsSecurityGroup
  - AwsSecurityGroupRule
  - AwsSnapshot
  - AwsSpotRequest
  - AwsTag
  - AwsUser
  - AwsVolume
  - ChefAccount
  - ChefCookbook
  - ChefCookbookVersion
  - ChefNode
  - AwsS3Bucket
  - AwsCloudFormationStack
  - AwsCloudFormationResource
  - ChefCookbookConstraint
  - ChefEnvironment
  - AwsRdsSnapshot
  - AwsVpc
  - AwsRedshiftCluster
  - AwsRedshiftSnapshot
  - AwsRedshiftReservedNode
  - AwsVpcSubnet
  - AwsLoadBalancer
  - AwsDynamoDbTable
  - AwsCacheCluster
  - InstanceAttributeHash
  - InstanceFileSystem
  - PuppetAccount
  - PuppetNode
  - PuppetClass
  - AwsRdsInstanceReservation
  - AwsRdsSecurityGroup
  - AwsRdsSecurityGroupRule
  - AwsRdsSubnetGroup
  - AwsInstanceReservationModification
  - AwsInstanceReservationModificationItem
  - AwsEmrCluster
  - AwsEmrClusterInstanceGroup
  - AwsEmrClusterInstance
  - AwsInstanceReservationListing
  - PagerdutyAccount
  - PagerdutyIncident
  - AwsNaclTable
  - AwsNaclRule
  - AwsCustomerGateway
  - AwsVpnGateway
  - AwsVpnConnection
  - AwsInternetGateway
  - AwsEni
  - AwsElasticIp
  - AwsEipPrivateIp
  - Alert
  - GcpComputeRegion
  - GcpComputeZone
  - GcpComputeProject
  - GcpComputeMachineType
  - GcpComputeInstance
  - GcpComputeDiskType
  - GcpComputeDisk
  - GcpComputeSnapshot
  - GcpComputeImage
  - GcpComputeAttachedDisk
  - GcpComputeMachineTypeProfile
  - GcpTag
  - GcpBillingStatement
  - GcpBillingStatementItem
  - GcpUsageStatement
  - GcpStorageBucket
  - VmwareAccount
  - VmwareFolder
  - VmwareDatacenter
  - VmwareHost
  - VmwareDatastore
  - VmwareVirtualMachine
  - VmwareCustomField
  - DockerImage
  - DockerContainer
  - DelegatedAction
  - CloudFrontDistribution
  - CloudFrontOrigin
  - DataCenterAccount
  - DataCenterServer
  - DataCenterServerFileSystem
  - AzureEnrollment
  - AzureBillingStatementItem
  - AzureStoredBill
  - AzureVm
  - DataCenterServerNetworkInterface
  - DataCenterServerCpu
  - DataCenterServerBlockDevice
  - AlertlogicAccount
  - AwsRoute53HostedZone
  - AnsibleAccount
  - AnsibleNode
  - AwsConfigRule
  - AwsConfigRuleEvaluationResult
  - AwsElasticacheReservedNode
  - DatadogAccount
  - DatadogHost
  - DatadogTag
  - AzureSubscription
  - AzureTag
  - AwsLambdaFunction
  - AzureAccount
  - AzureDepartment
  - AzureCostCenter
  - NewrelicAccount
  - NewrelicServer
  - IntegrationTag
  - AzureZone
  - AzureRegion
  - AzureResourceGroup
  - AzureServicePrincipal
  - AzureVmFileSystem
  - AzureVmNetworkInterface
  - AzureVmCpu
  - AzureVmVirtualDisk
  - AzureVmSize
  - AzureCatalog
  - AzureVmRate
  - AzureOffer
  - AzureRateCard
  - AzureStoredUsage
  - AwsIamPolicy
  - AwsIamRole
  - AwsIamServerCertificate
  - AwsAdsAgentStat
  - AwsAdsServer
  - AwsAccountRegionAttribute
  - AwsAdsProcess
  - AwsAdsConnection
  - DataCenterTag
  - CustomerTag
  - AwsIamCredentialReport
  - AzureCloudService
  - AzureSecurityGroup
  - AzureSecurityRule
  - AzureIpAddress
  - AwsIamPasswordPolicy
  - AzureStorage
  - AzureVmScaleSet
  - AwsCloudtrailTrail
  - AzureSqlServer
  - AzureSqlDatabase
  - AzurePartnerCenter
  - AzureRedisCache
  - JiraAccount
  - IntegrationOauthAccount
  - AzurePartnerCustomer
  - IntegrationMetadata
  - AzureVirtualNetworkGateway
  - AzureAppServicePlan
  - AzureServiceBusNamespace
  - AzureVirtualNetwork
  - AzureBatchAccount
  - AzureBackupVault
  - AzureRecoveryServicesVault
  - AzureHdInsightCluster
  - AzureSearchService
  - AzureSqlDataWarehouse
  - AzureStorSimpleDeviceManager
  - AzureAppService
  - AzureLogAnalyticsWorkspace
  - AzureExpressRouteCircuit
  - AzureCdnProfile
  - AwsNatGateway
  - AzureSnapshot
  - AzureNetworkInterface
  - AzureManagedDisk
  - AzureAppInsight
  - AwsElasticFileSystem
  - AzureDocumentDb
  - AzureKeyVault
  - AwsElasticsearchDomain
  - AwsElasticsearchInstance
  - AwsElasticsearchVolume
  - AwsDedicatedHost
  - AzureApplicationGateway
  - AwsConfigSetting
  - AwsWorkspace
  - AzureAppServiceEnvironment
  - AwsAutoScalingGroup
  - AwsKinesisStream
  - AzureVmReservationRate
  - AzureReservationOrder
  - AzureReservation
  - AzureVmRiQuote
---