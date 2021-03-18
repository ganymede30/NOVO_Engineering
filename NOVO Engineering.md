# Accel Auto Repair Shop
This is the description of classes and interfaces created for Accel Auto Repair Shop

## Mechanic (Interface)
This interface contains the behaviour of a mechanic in the shop. It is an interface, because I wanted to make my design flexible and by adapting to this interface other employees of the shop can behave like the mechanic.

## Customer
Customer is also an interface. Its primary responsibility is to enqueue  the vehicle repairing.

## InspectionQueueable
This is also an interface.  It contains two functions for adding and removing the vehicle in the queue. When the paper is added successfully, it should return true. When dequeing a vehicle it should return the Vehicle instance.

## VehicleInspectionReportable
VehicleInspectionReportable is an interface which contains the function for reporting result of inspection of a particular vehicle.

## Inspections
Inspections is an enumeration which contains the type of repair a vehicle needs. It's possible values are expiration **acceleration**, **deceleration** and **both**.

## Vehicle
It's a concrete class which contains the information of a vehicle.

## TestResults
This is also a concrete class which only contains the vehicle, and tyep of inspections which were asked about the vehile. 

## VehiclesQueue
VehicleQueue is the concrete implementation of inspection enqueble protocol.
Tunes the vehicle which needs repairing or they are waiting for the inspection.

## VehicleInspectionReporter
VehicleInspectionReporter of class responsible for reporting the details after inspection of the vehicle. This class will be handling responsibility of making the result presentable for the user. Not only this clause will make the inspection result presentable but it will be responsible for displaying inspections results to the user.

## Shop
Shop is a concrete laws which contains references to mechanics, vehicles for repairing and list of customers. This class doesn't do much by itself but it delegates it's responsibilities to different components of the system. This is responsible for communication between all the sub-components of the sub-models of the system.

# Applied SOLID principles
In the UML diagram I have tried to follow all the solid principles. The principles that I have applied is the
1. **Single responsibility principle**. By following the single responsibility principle I made sure that, one class should do one only one thing. So I created different classes for handling different responsibilities in the system, which are focused on doing one only one thing.
e.g. customer class does nothing except then enqueing a Vehicle in the shop, and VehicleInspectionReporter class only displays or formats the input

2. **Open Closed principle** Applied open closed principle for vehicle inspection details. The class **VehicleInspectionReporter** implements/conforms the **VehicleInspectionReportable** interface/protocol. In future we have to need new kind of reporting then we don't have to change the existing code anymore, we will create a new class and implement the new reporting feature in the class instead.

