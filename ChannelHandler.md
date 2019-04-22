# ChannelHandler

Handles an I/O event or intercepts an I/O operation,
and forwards it to its next handler in its {@link ChannelPipeline}.

# ChannelInboundHandler



# ChannelHandlerAdapter

ChannelHandlerAdapter implements ChannelHandler


# ChannelInitializer

  ChannelInitializer<C extends Channel> extends ChannelInboundHandlerAdapte
  
  initChannel
  
  

# ChannelInboundHandlerAdapter

ChannelInboundHandlerAdapter extends ChannelHandlerAdapter implements ChannelInboundHandler  


# ChannelPipeline

A list of {@link ChannelHandler}s
Each channel has its own pipeline and it is created automatically when a new channel is created.



event propagation







# ChannelHandlerContext

  ChannelHandlerContext extends AttributeMap, ChannelInboundInvoker, ChannelOutboundInvoker
  
  
  


