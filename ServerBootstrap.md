


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
                ch.eventLoop().execute(new Runnable() {
                @Override
                public void run() {
                    pipeline.addLast(new ServerBootstrapAcceptor(
                            ch, currentChildGroup, currentChildHandler, currentChildOptions, currentChildAttrs));
                }
            });
        ChannelFuture regFuture = config().group().register(channel);    
        promise.channel().unsafe().register(this, promise);
        

    
  sync
  
  
  Unsafe
  
    void register(EventLoop eventLoop, ChannelPromise promise);
  
  




