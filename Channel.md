
# channel  

channelFactory
       
       
ReflectiveChannelFactory

    public T newChannel() {
        try {
            return clazz.getConstructor().newInstance();
        } catch (Throwable t) {
            throw new ChannelException("Unable to create Channel from class " + clazz, t);
        }
    }
    

NioServerSocketChannel

  NioServerSocketChannel extends AbstractNioMessageChannel
                             implements io.netty.channel.socket.ServerSocketChannel           
  SelectableChannel                             


SelectableChannel

  SelectorProvider provider();


ServerSocketChannel
  
  ServerSocketChannel extends ServerChannel


ServerChannel

  ServerChannel extends Channel


Channel

  public interface Channel extends AttributeMap, ChannelOutboundInvoker, Comparable<Channel> {

      EventLoop eventLoop();

