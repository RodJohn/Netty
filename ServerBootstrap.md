


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
        

  
    doBind0
    private static void doBind0(
            final ChannelFuture regFuture, final Channel channel,
            final SocketAddress localAddress, final ChannelPromise promise) {

        // This method is invoked before channelRegistered() is triggered.  Give user handlers a chance to set up
        // the pipeline in its channelRegistered() implementation.
        channel.eventLoop().execute(new Runnable() {
            @Override
            public void run() {
                if (regFuture.isSuccess()) {
                    channel.bind(localAddress, promise).addListener(ChannelFutureListener.CLOSE_ON_FAILURE);
                } else {
                    promise.setFailure(regFuture.cause());
                }
            }
        });
    }


    
  sync
  
  
  Unsafe
  
    void register(EventLoop eventLoop, ChannelPromise promise);
  
  















# 关键节点

initAndRegister
channelFactory.newChannel
init(channel);
config().group().register(channel)
ch.register(selector, interestOps, task);
promise.channel().unsafe().register(this, promise);






