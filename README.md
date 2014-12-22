@startuml
box "Gossip Communicate" #LightBlue
    participant NodeA
    participant NodeB
end box
participant NodeC
participant NodeD

NodeA -> NodeB: GossipDigestSyn
NodeB -> NodeA: GossipDigestAck
activate NodeA
NodeA -> NodeC: Echo
NodeA -> NodeD: Echo
NodeA -> NodeB: GossipDigestAck2
deactivate NodeA
activate NodeB
NodeB -> NodeC: Echo
NodeB -> NodeD: Echo
deactivate NodeB
@enduml
