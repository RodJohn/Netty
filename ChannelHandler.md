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


DefaultChannelPipeline


    final AbstractChannelHandlerContext head;
    final AbstractChannelHandlerContext tail;

    private final Channel channel;
    private final ChannelFuture succeededFuture;
    
    
    
    public final ChannelPipeline addLast(EventExecutorGroup group, String name, ChannelHandler handler) {
        final AbstractChannelHandlerContext newCtx;
        synchronized (this) {
            newCtx = newContext(group, filterName(name, handler), handler);
              //new DefaultChannelHandlerContext(this, childExecutor(group), name, handler);
            addLast0(newCtx);    
    









# ChannelHandlerContext


DefaultChannelHandlerContext
 
   final class DefaultChannelHandlerContext extends AbstractChannelHandlerContext {
      private final ChannelHandler handler;
  

AbstractChannelHandlerContext

  abstract class AbstractChannelHandlerContext extends DefaultAttributeMap
          implements ChannelHandlerContext, ResourceLeakHint {

      private static final InternalLogger logger = InternalLoggerFactory.getInstance(AbstractChannelHandlerContext.class);
      volatile AbstractChannelHandlerContext next;
      volatile AbstractChannelHandlerContext prev;


ChannelHandlerContext

  public interface ChannelHandlerContext extends AttributeMap, ChannelInboundInvoker, ChannelOutboundInvoker {

      Channel channel();

      EventExecutor executor();

      ChannelHandler handler();

