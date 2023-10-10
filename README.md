# CAPWS
BTP CAP Enablement workshop 2023

CAP Manual & Jumpstart
https://cap.cloud.sap/

(1) Composition of Many
entity XTBL003 {
key FLOWUUID : UUID @(Core.Computed : true);
key FLOWCODE : String(5);
key STATUS : String(2);
DETAIL : Composition of many XTBL004
  on DETAIL.FLOWUUID = FLOWUUID
  and DETAIL.FLOWCODE = FLOWCODE
  and DETAIL.STATUS = STATUS; 
FIELD01 : String(100);
FIELD02 : String(100);
} 

entity XTBL004 {
key FLOWUUID : UUID @(Core.Computed : true);
key FLOWCODE : String(5);
key NO1 : String(2);
STATUS : String(2);
APPROVAL_NAME : String(100);
} 


----
{
 "FLOWCODE": "MH001",
 "STATUS": "01", 
 "FIELD01": "07199782",
 "FIELD02": "K0121120",
 "DETAIL" : [
  {
    "FLOWCODE": "MH001",
    "NO1": "2",
    "STATUS": "01", 
    "APPROVAL_NAME": "JHAN"
   },{
   "FLOWCODE": "MH001",
   "NO1": "3",
   "STATUS": "01", 
   "APPROVAL_NAME": "JHAN"
  }]
}

/hkmc/XTBL003(FLOWUUID=50a79a4e-834f-4294-9d4c-c415fbc572c4,FLOWCODE='MH001',STATUS='01')?$expand=DETAIL


(2) Composition of one
entity XTBL0030 {
key FLOWUUID : UUID @(Core.Computed : true);
key FLOWCODE : String(5);
key STATUS : String(2);
DETAIL : Composition of one XTBL004
  on DETAIL.FLOWUUID = FLOWUUID
  and DETAIL.FLOWCODE = FLOWCODE
  and DETAIL.STATUS = STATUS; 
FIELD01 : String(100);
FIELD02 : String(100);
} 
entity XTBL0040 {
key FLOWUUID : UUID @(Core.Computed : true);
key FLOWCODE : String(5);
key NO1 : String(2);
STATUS : String(2);
APPROVAL_NAME : String(100);
} 


