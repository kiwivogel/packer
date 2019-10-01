<!-- Code generated from the comments of the Config struct in builder/amazon/ebssurrogate/builder.go; DO NOT EDIT MANUALLY -->

-   `ami_block_device_mappings` (awscommon.BlockDevices) - Add one or more block device mappings to the AMI. These will be attached
    when booting a new instance from your AMI. To add a block device during
    the Packer build see `launch_block_device_mappings` below. Your options
    here may vary depending on the type of VM you use. See the
    [BlockDevices](#block-devices-configuration) documentation for fields.
    
-   `launch_block_device_mappings` (BlockDevices) - Add one or more block devices before the Packer build starts. If you add
    instance store volumes or EBS volumes in addition to the root device
    volume, the created AMI will contain block device mapping information
    for those volumes. Amazon creates snapshots of the source instance's
    root volume and any other EBS volumes described here. When you launch an
    instance from this new AMI, the instance automatically launches with
    these additional volumes, and will restore them from snapshots taken
    from the source instance. See the
    [BlockDevices](#block-devices-configuration) documentation for fields.
    
-   `run_volume_tags` (awscommon.TagMap) - Tags to apply to the volumes that are *launched* to create the AMI.
    These tags are *not* applied to the resulting AMI unless they're
    duplicated in `tags`. This is a [template
    engine](/docs/templates/engine.html), see [Build template
    data](#build-template-data) for more information.
    
-   `ami_architecture` (string) - what architecture to use when registering the
    final AMI; valid options are "x86_64" or "arm64". Defaults to "x86_64".
    