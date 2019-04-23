
# JUC Future

	isDone();

	get()


# Future

	interface Future<V> extends java.util.concurrent.Future<V> {

	boolean isSuccess();

	addListener

	sync

	getNow
	
	

# Promise

	Special {@link Future} which is writable.	
	Promise<V> extends Future<V>


	setSuccess
	
	

# DefaultPromise

  private final EventExecutor executor;



    @Override
    public Promise<V> setSuccess(V result) {
        if (setSuccess0(result)) {
            notifyListeners();
            return this;
        }
        throw new IllegalStateException("complete already: " + this);
    }


    private void notifyListeners() {
        EventExecutor executor = executor();
        if (executor.inEventLoop()) {
            final InternalThreadLocalMap threadLocals = InternalThreadLocalMap.get();
            final int stackDepth = threadLocals.futureListenerStackDepth();
            if (stackDepth < MAX_LISTENER_STACK_DEPTH) {
                threadLocals.setFutureListenerStackDepth(stackDepth + 1);
                try {
                    notifyListenersNow();
                } finally {
                    threadLocals.setFutureListenerStackDepth(stackDepth);
                }
                return;
            }
        }

        safeExecute(executor, new Runnable() {
            @Override
            public void run() {
                notifyListenersNow();
            }
        });
    }


    private static void notifyListener0(Future future, GenericFutureListener l) {
        try {
            l.operationComplete(future);
        } catch (Throwable t) {
            logger.warn("An exception was thrown by " + l.getClass().getName() + ".operationComplete()", t);
        }
    }



# ChannelPromise

	ChannelPromise extends ChannelFuture, Promise<Void>
	
	Channel channel();
	
	
	
# DefaultChannelPromise

	DefaultChannelPromise extends DefaultPromise<Void> implements ChannelPromise, FlushCheckpoint 
	
	
	

