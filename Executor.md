







# EventLoopGroup

ChannelFuture register(Channel channel);



# NioEventLoopGroup

  MultithreadEventExecutorGroup

    children = new EventExecutor[nThreads];（NioEventLoop）
    EventExecutorChooserFactory chooserFactory
  
    final FutureListener<Object> terminationListener = new FutureListener<Object>() {
      @Override
      public void operationComplete(Future<Object> future) throws Exception {
          if (terminatedChildren.incrementAndGet() == children.length) {
              terminationFuture.setSuccess(null);
          }
      }
    };




# NioEventLoop

NioEventLoop extends SingleThreadEventLoop
  private Selector selector;
  void select(boolean oldWakenUp)
  public void register(final SelectableChannel ch, final int interestOps, final NioTask<?> task)
  ch.register(selector, interestOps, task);
    
 
 ## SingleThreadEventLoop


Queue<Runnable> tailTasks

 register(new DefaultChannelPromise(channel, this));
 
 promise.channel().unsafe().register(this, promise);



SingleThreadEventExecutor




# Executor

Executor
  void execute(Runnable command);
ThreadPerTaskExecutor
  ThreadFactory
  void execute(Runnable command) {
        threadFactory.newThread(command).start();
    }
DefaultThreadFactory
  Thread newThread(Runnable r, String name) {
        return new FastThreadLocalThread(threadGroup, r, name);
    }
FastThreadLocalThread extends Thread 


# EventExecutorChooserFactory

DefaultEventExecutorChooserFactory implements EventExecutorChooserFactory

EventExecutorChooser newChooser(EventExecutor[] executors)

    interface EventExecutorChooser {

        /**
         * Returns the new {@link EventExecutor} to use.
         */
        EventExecutor next();
    }


# FutureListener

FutureListener<V> extends GenericFutureListener<Future<V>> { }

/**
 * Listens to the result of a {@link Future}.  The result of the asynchronous operation is notified once this listener
 * is added by calling {@link Future#addListener(GenericFutureListener)}.
 */
public interface GenericFutureListener<F extends Future<?>> extends EventListener {
    void operationComplete(F future) throws Exception;
}


# Future

/**
 * The result of an asynchronous operation.
 */
@SuppressWarnings("ClassNameSameAsAncestorName")
public interface Future<V> extends java.util.concurrent.Future<V>

  Future<V> addListener(GenericFutureListener<? extends Future<? super V>> listener);

  
