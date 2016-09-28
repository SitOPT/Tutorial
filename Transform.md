# Transformation

This is a tutorial for transforming a template between Node-Red and Esper.

## Node-Red to Esper

### Requirements

 - Only ``sensor`` in all Context Nodes in ``inputType``
 - All Condition Nodes' ``opType`` must have one of the following values:
      - lowerThan
      - greaterThan
      - equals
      - notEquals
      - between
 - No Operation Nodes with XOR
 
### Transformation

 - Remove the ``negated``-Field in Operation Nodes
 - Move the ``measureName``- and ``unit``-Element from ContextNodes to ConditionNodes
 - Remove the ``inputType``-Field from ContextNodes
 - Rename ``condValues`` to ``condValue`` in Condition Nodes
 - Wrap all Nodes in into a ``situation``-Element. It has following Attributes:
     - id - The id of the situation
     - name - The name of the situation
 

## Esper to Node-Red

### Requirements

 - No Comparison between two Context Nodes
 - No aggregation
 
### Transformation

 - Add a ``negated``-Element in Operation Nodes with the value ``false``
 - Move the ``measureName``- and ``unit``-Element from ConditionNodes to ContextNodes
 - Add an ``inputType``-Field to ContextNodes and set the value to ``sensor``
 - Rename ``condValue`` to ``condValues`` in ConditionNodes
 - Remove the ``situation``-Element but leave its content