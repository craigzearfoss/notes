# Vue Lifecycle Hooks

### beforeCreate
- Called synchronously immediately after the instance has been initialized, before data observation and event/watcher setup.
  
### created
- Called synchronously after the instance is created.

### beforeMount
- Called right before the mounting begins: the render function is about to be called for the first time.

### mounted
- Called after the instance has been mounted, where el is replaced by the newly created vm.\$el.

### beforeDestroy
- Called right before a Vue instance is destroyed. At this stage the instance is still fully functional.

### destroyed
- Called after a Vue instance has been destroyed.
