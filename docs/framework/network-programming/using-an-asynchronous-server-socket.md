---
title: 非同期サーバー ソケットの使用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- sockets, asynchronous server sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- asynchronous server sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
ms.openlocfilehash: 467804e685d800643c421ed1aad040a842b42886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180633"
---
# <a name="using-an-asynchronous-server-socket"></a><span data-ttu-id="78574-102">非同期サーバー ソケットの使用</span><span class="sxs-lookup"><span data-stu-id="78574-102">Using an Asynchronous Server Socket</span></span>
<span data-ttu-id="78574-103">非同期サーバー ソケットは、.NET Framework の非同期プログラミング モデルを使用してネットワーク サービス要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="78574-103">Asynchronous server sockets use the .NET Framework asynchronous programming model to process network service requests.</span></span> <span data-ttu-id="78574-104"><xref:System.Net.Sockets.Socket> クラスは、標準の .NET Framework の非同期名前付けパターンに従います。たとえば、同期の <xref:System.Net.Sockets.Socket.Accept%2A> メソッドは非同期の <xref:System.Net.Sockets.Socket.BeginAccept%2A> メソッドと <xref:System.Net.Sockets.Socket.EndAccept%2A> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="78574-104">The <xref:System.Net.Sockets.Socket> class follows the standard .NET Framework asynchronous naming pattern; for example, the synchronous <xref:System.Net.Sockets.Socket.Accept%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginAccept%2A> and <xref:System.Net.Sockets.Socket.EndAccept%2A> methods.</span></span>  
  
 <span data-ttu-id="78574-105">非同期サーバー ソケットには、ネットワークからの接続要求の受け入れを開始するメソッド、接続要求を処理してネットワークからデータの受信を開始するコールバック メソッド、データの受信を終了するコールバック メソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="78574-105">An asynchronous server socket requires a method to begin accepting connection requests from the network, a callback method to handle the connection requests and begin receiving data from the network, and a callback method to end receiving the data.</span></span> <span data-ttu-id="78574-106">このセクションでは、このそれぞれについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="78574-106">All these methods are discussed further in this section.</span></span>  
  
 <span data-ttu-id="78574-107">次の例では、ネットワークから接続要求の受け入れを開始するために、メソッド `StartListening` で **Socket** を初期化してから、**BeginAccept** メソッドを使用して新しい接続の受け入れを開始します。</span><span class="sxs-lookup"><span data-stu-id="78574-107">In the following example, to begin accepting connection requests from the network, the method `StartListening` initializes the **Socket** and then uses the **BeginAccept** method to start accepting new connections.</span></span> <span data-ttu-id="78574-108">ソケットで新しい接続要求を受信すると、accept のコールバック メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="78574-108">The accept callback method is called when a new connection request is received on the socket.</span></span> <span data-ttu-id="78574-109">このコールバック メソッドは、接続を処理する **Socket** インスタンスを取得し、要求を処理するスレッドに **Socket** を渡す役割を持ちます。</span><span class="sxs-lookup"><span data-stu-id="78574-109">It is responsible for getting the **Socket** instance that will handle the connection and handing that **Socket** off to the thread that will process the request.</span></span> <span data-ttu-id="78574-110">accept のコールバック メソッドは <xref:System.AsyncCallback> デリゲートを実装しており、void を返して <xref:System.IAsyncResult> 型の 1 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="78574-110">The accept callback method implements the <xref:System.AsyncCallback> delegate; it returns a void and takes a single parameter of type <xref:System.IAsyncResult>.</span></span> <span data-ttu-id="78574-111">accept のコールバック メソッドのシェルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78574-111">The following example is the shell of an accept callback method.</span></span>  
  
```vb  
Sub AcceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'AcceptCallback  
```  
  
```csharp  
void AcceptCallback(IAsyncResult ar)
{  
    // Add the callback code here.  
}  
```  
  
 <span data-ttu-id="78574-112">**BeginAccept** メソッドは 2 つのパラメーターを受け取ります。accept のコールバック メソッドを示す **AsyncCallback** デリゲートと、状態情報をコールバック メソッドに渡すために使用されるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="78574-112">The **BeginAccept** method takes two parameters, an **AsyncCallback** delegate that points to the accept callback method and an object that is used to pass state information to the callback method.</span></span> <span data-ttu-id="78574-113">次の例では、リッスンしている **Socket** が *state* パラメーターを使用してコールバック メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="78574-113">In the following example, the listening **Socket** is passed to the callback method through the *state* parameter.</span></span> <span data-ttu-id="78574-114">この例では、**AsyncCallback** デリゲートを作成し、ネットワークから接続の受け入れを開始します。</span><span class="sxs-lookup"><span data-stu-id="78574-114">This example creates an **AsyncCallback** delegate and starts accepting connections from the network.</span></span>  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.AcceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
```  
  
 <span data-ttu-id="78574-115">非同期ソケットは、システム スレッド プールの複数のスレッドを使用して、受信接続を処理します。</span><span class="sxs-lookup"><span data-stu-id="78574-115">Asynchronous sockets use threads from the system thread pool to process incoming connections.</span></span> <span data-ttu-id="78574-116">接続の受け入れに使用されるスレッド、各受信接続の処理に使用されるスレッド、接続からデータを受け取るために使用されるスレッドがあります。</span><span class="sxs-lookup"><span data-stu-id="78574-116">One thread is responsible for accepting connections, another thread is used to handle each incoming connection, and another thread is responsible for receiving data from the connection.</span></span> <span data-ttu-id="78574-117">スレッド プールが割り当てるスレッドによっては、これらのスレッドが同じスレッドになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78574-117">These could be the same thread, depending on which thread is assigned by the thread pool.</span></span> <span data-ttu-id="78574-118">次の例では、<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> クラスがメイン スレッドの実行を停止し、実行を続行できるようになったらシグナルを送ります。</span><span class="sxs-lookup"><span data-stu-id="78574-118">In the following example, the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class suspends execution of the main thread and signals when execution can continue.</span></span>  
  
 <span data-ttu-id="78574-119">ローカル コンピューター上に非同期 TCP/IP Socket を作成し、接続の受け入れを開始する非同期メソッドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78574-119">The following example shows an asynchronous method that creates an asynchronous TCP/IP socket on the local computer and begins accepting connections.</span></span> <span data-ttu-id="78574-120">**というグローバル**ManualResetEvent`allDone` があり、メソッドが `SocketListener` というクラスのメンバーであり、`AcceptCallback` というコールバック メソッドが定義されているとします。</span><span class="sxs-lookup"><span data-stu-id="78574-120">It assumes that there is a global **ManualResetEvent** named `allDone`, that the method is a member of a class named `SocketListener`, and that a callback method named `AcceptCallback` is defined.</span></span>  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine($"Local address and port : {localEP.ToString()}")  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.AcceptCallback), _  
                listener)  
  
            allDone.WaitOne()  
        End While  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
    Console.WriteLine("Closing the listener...")  
End Sub 'StartListening  
```  
  
```csharp  
public void StartListening()
{  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0], 11000);  
  
    Console.WriteLine($"Local address and port : {localEP.ToString()}");  
  
    Socket listener = new Socket(localEP.Address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);  
  
    try
    {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true)
        {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
  
            allDone.WaitOne();  
        }  
    }
    catch (Exception e)
    {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine("Closing the listener...");  
}  
```  
  
 <span data-ttu-id="78574-121">accept のコールバック メソッド (前の例では `AcceptCallback`) は、処理を継続するためにメイン アプリケーション スレッドにシグナルを送り、クライアントとの接続を確立し、クライアントからデータの非同期読み取りを開始します。</span><span class="sxs-lookup"><span data-stu-id="78574-121">The accept callback method (`AcceptCallback` in the preceding example) is responsible for signaling the main application thread to continue processing, establishing the connection with the client, and starting the asynchronous read of data from the client.</span></span> <span data-ttu-id="78574-122">次の例は、`AcceptCallback` メソッドの実装の最初の部分です。</span><span class="sxs-lookup"><span data-stu-id="78574-122">The following example is the first part of an implementation of the `AcceptCallback` method.</span></span> <span data-ttu-id="78574-123">このメソッドのセクションでは、処理を継続するためにメイン アプリケーション スレッドに信号を送り、クライアントへの接続を確立しています。</span><span class="sxs-lookup"><span data-stu-id="78574-123">This section of the method signals the main application thread to continue processing and establishes the connection to the client.</span></span> <span data-ttu-id="78574-124">**というグローバル**ManualResetEvent`allDone` があるとします。</span><span class="sxs-lookup"><span data-stu-id="78574-124">It assumes a global **ManualResetEvent** named `allDone`.</span></span>  
  
```vb  
Public Sub AcceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'AcceptCallback  
```  
  
```csharp  
public void AcceptCallback(IAsyncResult ar)
{  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.
}  
```  
  
 <span data-ttu-id="78574-125">クライアント ソケットからデータを読み取るには、非同期呼び出しの間で値を渡す状態オブジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="78574-125">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="78574-126">次の例では、リモート クライアントから文字列を受信する状態オブジェクトを実装しています。</span><span class="sxs-lookup"><span data-stu-id="78574-126">The following example implements a state object for receiving a string from the remote client.</span></span> <span data-ttu-id="78574-127">クライアント ソケットのフィールド、データを受信するデータ バッファー、クライアントから送信されるデータ文字列を作成する <xref:System.Text.StringBuilder> が含まれています。</span><span class="sxs-lookup"><span data-stu-id="78574-127">It contains fields for the client socket, a data buffer for receiving data, and a <xref:System.Text.StringBuilder> for creating the data string sent by the client.</span></span> <span data-ttu-id="78574-128">これらのフィールドを状態オブジェクトに格納することで、複数の呼び出し間で値を保持し、クライアント ソケットからデータ読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="78574-128">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject
{  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 <span data-ttu-id="78574-129">クライアント ソケットからデータの受信を開始する `AcceptCallback` メソッドのセクションでは、まず `StateObject` クラスのインスタンスを初期化してから、<xref:System.Net.Sockets.Socket.BeginReceive%2A> メソッドを呼び出してクライアント ソケットからデータの読み取りを非同期に開始します。</span><span class="sxs-lookup"><span data-stu-id="78574-129">The section of the `AcceptCallback` method that starts receiving the data from the client socket first initializes an instance of the `StateObject` class and then calls the <xref:System.Net.Sockets.Socket.BeginReceive%2A> method to start reading the data from the client socket asynchronously.</span></span>  
  
 <span data-ttu-id="78574-130">`AcceptCallback` メソッドのサンプル コード全体を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78574-130">The following example shows the complete `AcceptCallback` method.</span></span> <span data-ttu-id="78574-131">**クラスが定義されている** というグローバル `allDone,`ManualResetEvent`StateObject` があり、`ReadCallback` メソッドが `SocketListener` というクラスで定義されているとします。</span><span class="sxs-lookup"><span data-stu-id="78574-131">It assumes that there is a global **ManualResetEvent** named `allDone,` that the `StateObject` class is defined, and that the `ReadCallback` method is defined in a class named `SocketListener`.</span></span>  
  
```vb  
Public Shared Sub AcceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.ReadCallback, state)  
End Sub 'AcceptCallback  
```  
  
```csharp  
public static void AcceptCallback(IAsyncResult ar)
{  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.ReadCallback), state);  
}  
```  
  
 <span data-ttu-id="78574-132">非同期ソケット サーバーのために実装が必要な最後のメソッドは、クライアントから送信されたデータを返す read のコールバック メソッドです。</span><span class="sxs-lookup"><span data-stu-id="78574-132">The final method that needs to be implemented for the asynchronous socket server is the read callback method that returns the data sent by the client.</span></span> <span data-ttu-id="78574-133">accept のコールバック メソッドと同様に、read のコールバック メソッドは **AsyncCallback** デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="78574-133">Like the accept callback method, the read callback method is an **AsyncCallback** delegate.</span></span> <span data-ttu-id="78574-134">このメソッドは、クライアント ソケットからデータ バッファーに 1 から数バイトのデータを読み取ってから、クライアントから送信されたデータが完了するまで、**BeginReceive** メソッドを再び呼び出します。</span><span class="sxs-lookup"><span data-stu-id="78574-134">This method reads one or more bytes from the client socket into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="78574-135">メッセージ全体がクライアントから読み取られたら、コンソールに文字列が表示され、クライアントへの接続を処理するサーバー ソケットが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="78574-135">Once the entire message has been read from the client, the string is displayed on the console and the server socket handling the connection to the client is closed.</span></span>  
  
 <span data-ttu-id="78574-136">`ReadCallback` メソッドを実装する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78574-136">The following sample implements the `ReadCallback` method.</span></span> <span data-ttu-id="78574-137">`StateObject` クラスが定義されているとします。</span><span class="sxs-lookup"><span data-stu-id="78574-137">It assumes that the `StateObject` class is defined.</span></span>  
  
```vb  
Public Shared Sub ReadCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReadCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine($"Read {content.Length} bytes from socket. {ControlChars.Cr} Data : {content}")  
        End If  
    End If  
End Sub 'ReadCallback  
```  
  
```csharp  
public static void ReadCallback(IAsyncResult ar)
{  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0)
    {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReadCallback), state);  
    }
    else
    {  
        if (state.sb.Length > 1)
        {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine($"Read {content.Length} bytes from socket.\n Data : {content}");
        }  
        handler.Close();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="78574-138">参照</span><span class="sxs-lookup"><span data-stu-id="78574-138">See also</span></span>

- [<span data-ttu-id="78574-139">同期サーバー ソケットの使用</span><span class="sxs-lookup"><span data-stu-id="78574-139">Using a Synchronous Server Socket</span></span>](using-a-synchronous-server-socket.md)
- [<span data-ttu-id="78574-140">非同期サーバー ソケットの例</span><span class="sxs-lookup"><span data-stu-id="78574-140">Asynchronous Server Socket Example</span></span>](asynchronous-server-socket-example.md)
- [<span data-ttu-id="78574-141">スレッド化</span><span class="sxs-lookup"><span data-stu-id="78574-141">Threading</span></span>](../../standard/threading/index.md)
- [<span data-ttu-id="78574-142">リッスン (ソケットで)</span><span class="sxs-lookup"><span data-stu-id="78574-142">Listening with Sockets</span></span>](listening-with-sockets.md)
