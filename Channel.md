
# channel  

  

NioServerSocketChannel

  NioServerSocketChannel extends AbstractNioMessageChannel
                             implements io.netty.channel.socket.ServerSocketChannel  
                             
         SelectorProvider DEFAULT_SELECTOR_PROVIDER = SelectorProvider.provider();
         
         public NioServerSocketChannel() {
                this(newSocket(DEFAULT_SELECTOR_PROVIDER));
         }
         
         public NioServerSocketChannel(ServerSocketChannel channel) {
            super(null, channel, SelectionKey.OP_ACCEPT);
            config = new NioServerSocketChannelConfig(this, javaChannel().socket());
        }   
  
AbstractNioChannel

    private final SelectableChannel ch;
    protected final int readInterestOp;
    volatile SelectionKey selectionKey;
    boolean readPending;
    private final Runnable clearReadPendingRunnable = new Runnable() {
        @Override
        public void run() {
            clearReadPending0();
        }
    };
    private ChannelPromise connectPromise;
    private ScheduledFuture<?> connectTimeoutFuture;
    private SocketAddress requestedRemoteAddress;




AbstractChannel

    protected AbstractChannel(Channel parent) {
        this.parent = parent;
        id = newId();
        unsafe = newUnsafe();
        pipeline = newChannelPipeline();
    }


Channel

  public interface Channel extends AttributeMap, ChannelOutboundInvoker, Comparable<Channel> {

      EventLoop eventLoop();


# channelFactory

channelFactory
       
       
ReflectiveChannelFactory

    public T newChannel() {
        try {
            return clazz.getConstructor().newInstance();
        } catch (Throwable t) {
            throw new ChannelException("Unable to create Channel from class " + clazz, t);
        }
    }
  

# SelectableChannel

  SelectableChannel                             


SelectableChannel

  SelectorProvider provider();


ServerSocketChannel
  
  ServerSocketChannel extends ServerChannel


ServerChannel

  ServerChannel extends Channel
  
  
  
  
  
# SelectorProvider

Service-provider class for selectors and selectable channels.



