# Listener Management

## What are different type of Queue Management available for a JMS Listener?

***Point to Point Model*** is a normal Queue processing where a queue item comes and listener will read then the queue item removed from the queue JNDI folder.

***Publish and Subscribe Model*** is a Topic processing model where a queue item comes and there can be many subscribers listening to that topic. In a topic, the items are not deleted from the JNDI folder.

*PEGA Supports both type of model*
