


# ServerBootstrap


  group
    private volatile EventLoopGroup childGroup;

  channel
    
    private volatile ChannelHandler childHandler;
   
  childHandler
  
    ChannelInitializer
    initChannel
    
  bind
  
    initAndRegister
      channel = channelFactory.newChannel();
      init(channel);
        ChannelPipeline p = channel.pipeline();
         p.addLast
        
    
    
    
  sync
  
  
  




