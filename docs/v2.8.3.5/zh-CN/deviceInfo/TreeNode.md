## 功能模板

Utility的工程树中支持的节点类型会保存在deviceInfo.xml文件的TreeNodeTypes元素中。

	<TreeNodeTypes>
      <Type>RTU</Type>
      <Type>DAQ</Type>
      <Type>IOTag</Type>
      <Type>Board</Type>
	  ...
    </TreeNodeTypes>

当新增功能页面时，也需要在其中新增Type元素。

---

### 功能树结构

在deviceInfo.xml文件中表示每种设备类型的Node元素下，包含TreeNode元素描述功能树结构。Utility依照此结构创建每种设备的功能树。

TreeNode元素的Type属性对应TreeNodeTypes元素中Type。

可依据设备的不同需求增减TreeNode元素

	<TreeNode type="RTU">
      <TreeNode type="DAQ">
        <TreeNode type="IOTag">
          <TreeNode type="Ethernet"/>
          <TreeNode type="Zigbee"/>
        </TreeNode>
        <TreeNode type="SystemTag"/>
        <TreeNode type="CalcTag"/>
        <TreeNode type="LocalTag"/>
      </TreeNode>
      <TreeNode type="DataLogger">
        <TreeNode type="TagLogger"/>
      </TreeNode>
      <TreeNode type="Service">
        <TreeNode type="ModbusServer"/>
        <TreeNode type="DNP3Outstation"/>
        <TreeNode type="WASCADA"/>
        <TreeNode type="IEC104Server"/>
      </TreeNode>
      <TreeNode type="Connectivity">
        <TreeNode type="ActConn"/>
        <TreeNode type="OpenVPN"/>
      </TreeNode>
      <TreeNode type="DeviceConfig">
        <TreeNode type="NetworkConfig"/>
        <TreeNode type="NTPConfig"/>
        <TreeNode type="GPSConfig"/>
      </TreeNode>
    </TreeNode>