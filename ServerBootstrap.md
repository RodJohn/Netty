

# ServerBootstrap


  group
    private volatile EventLoopGroup childGroup;

  channel
    
    private volatile ChannelHandler childHandler;
   
  childHandler
  
    ChannelInitializer
    initChannel
    
  bind
    
    
    
# ReflectiveChannelFactory

    public T newChannel() {
        try {
            return clazz.getConstructor().newInstance();
        } catch (Throwable t) {
            throw new ChannelException("Unable to create Channel from class " + clazz, t);
        }
    }



