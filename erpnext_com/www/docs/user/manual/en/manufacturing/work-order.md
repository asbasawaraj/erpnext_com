<!-- add-breadcrumbs -->
# Work Order

**A Work Order is a signal to manufacture a certain quantity of a certain Item.**

Work order is the starting point in the manufacturing cycle.

You can create a work order:

* From a Production Plan.
* From a Sales Order.
* From a Material Request with Type as Manufacture.
* Directly without reference to any other document.

### 1. How to Create a Work Order

To create a new Work Order:

1. Go to **Manufacturing > Production > Work Order > New**.
1. Select the Item To Manufacture.
1. The default BOM of the item will be set in BOM No, if needed you can change it.
1. Enter the Qty To Manufacture.
1. Based on the BOM No and the Qty To Manufacture, raw material details will be set in Required Items table. If the BOM has operations listed, those details will be set in Operations table.
1. Select Warehouses:
  * Source Warehouses: The warehouse where you store your raw materials. Each required item can have separate source warehouse. Group warehouse also can be selected as source warehouse. On submission of Work Order, the raw materials will be reserved in these warehouses for production usage.
  * Work-in-Progress Warehouse: The warehouse to which Items will be transferred when you begin production. Group Warehouse can also be selected as Work-in-Progress warehouse.
  * Target Warehouse: The warehouse where you store finished Items before they are shipped.
  * Scrap Warehouse: Warehouse to which scrap items produced are to be transferred.
1. Mention the Planned Start Date and Expected Delivery Date.
1. Save and Submit.

You can save a Work Order without selecting the warehouses, but warehouses are mandatory for submitting a Work Order.

You can set the default Work-in-Progress and Finished Goods warehouse in [Manufacturing Settings](/docs/user/manual/en/manufacturing/manufacturing-settings).

<img class="screenshot" alt="Work Order" src="{{docs_base_url}}/assets/img/manufacturing/work-order.png">

### 2. Features

#### 2.1 Material Transfer Against Work Order

From a work order you can easily generate the Stock Entry to register the movement of materials listed in **Bill of Materials** from one warehouse to another warehouse.

* After submission the status of work order will be 'Not Started', click on 'Start' button to initiate the manufacturing process.
* In the 'Select Quantity' pop up window set the quantity of finished goods for which you would like to transfer the raw material.
* Stock Entry transaction with purpose 'Material Transfer for Manufacture' is prepared.
* Review and Submit.
* Status of the work order will be set to 'In Process'.
* Once the finished good is manufactured, click on Finish button and set the quantity.
* Stock Entry Transaction with purpose 'Manufacture' is prepared.
* Save and Submit.

<img class="screenshot" alt="Material Transfer Against Work Order" src="{{docs_base_url}}/assets/img/manufacturing/material_transfer_against_work_order.gif">

As described above, first material is transferred from stores to wip warehouse and then from wip to finished goods warehouse.
If transfer to wip warehouse is not required, you can check the 'Skip Material Transfer' check box, which will allow you to make the  Stock Entry with purpose 'Manufacture' directly by clicking on the ‘Finish’ button. This will deduct the raw material from stores and add the finished goods.


#### 2.2  Material Transfer Against Job Cards

If you have defined the operations needed to manufacture finished goods along with the raw materials required in the BOM, you can transfer material against each job card by setting 'Transfer Material Against' to Job Card.

<img class="screenshot" alt="Material Transfer Against Job Card" src="{{docs_base_url}}/assets/img/manufacturing/material_transfer_against_job_card.gif">

#### 2.3 Reassigning Workstation and Duration of Operations

By default the system fetches workstation and duration for Work Order operations from the selected BOM.

<img class="screenshot" alt="PO Opeartions" src="{{docs_base_url}}/assets/img/manufacturing/default_workstations.png">

If you wish to reassign the workstation for a particular operation and update the Operation Time in the Work Order, you can do so before submitting the Work Order.

<img class="screenshot" alt="PO reassigning Operations" src="{{docs_base_url}}/assets/img/manufacturing/PO-reassigning-operations.png">

###2.3 Stopping a Work Order

* When you stop a Work Order its status is changed to Stop indicating that all production process against that Work Order is to be ceased.
* To stop the Work Order click on the 'Stop' Button

  1. On Submitting the Work Order, the system will reserve a slot for each of the Work Order Operations serially after the planned start date based on the workstation availability. The Workstation availability depends on the Workstation timings, holiday list and if some other Work Order Operation was scheduled in that slot. You can mention the number of days for the system to try scheduling the operations in the Manufacturing Settings. This is set to 30 Days by default. If the operation requires time exceeding the available slot, system shall ask you to break the operations. Once the scheduling is done system shall create Time Logs and save them. You can Modify them and submit them later.
  2. You can also create additional time logs against an Operation. For doing so select the respective operation and click on 'Make Time Log'
  3. Transfer Raw Material: This will create a Stock Entry with all the Items required to complete this Work Order to be added to the WIP Warehouse. (this will add sub-Items with BOM as one Item or explode their children based on your setting above).
  4. Update Finished Goods: This will create a Stock Entry that will deduct all the sub-Items from the WIP Warehouse and add them to the Finished Goods Warehouse.
  5. To check all Time Logs made against the Work Order click on 'Show Time Logs'

<img class="screenshot" alt="PO - stop" src="{{docs_base_url}}/assets/img/manufacturing/PO-stop.png">

* You can also re-start a stopped Work Order.

<div class-"embed-container">
  <iframe src="https://www.youtube.com/embed/yv_KAIlHrO4?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen>
  </iframe>
</div>

<img class="screenshot" alt="Work Order" src="{{docs_base_url}}/assets/img/manufacturing/manufacturing-flow.png">


{next}
