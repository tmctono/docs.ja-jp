---
title: '方法: ネットワークのトレースを構成する'
ms.date: 03/30/2017
helpviewer_keywords:
- formatting [.NET Framework], network tracing
- network tracing, configuring
- level attribute
- app.config files, network tracing
- configuration files [.NET Framework], network tracing
- protocol-level trace output
- application configuration files, network tracing
- sockets, trace output
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
ms.openlocfilehash: dc9b6b5399063026c0bbe5735964ed42a21168fa
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048368"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="e6737-102">方法: ネットワークのトレースを構成する</span><span class="sxs-lookup"><span data-stu-id="e6737-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="e6737-103">アプリケーションまたはコンピューターの構成ファイルには、ネットワークのトレースの形式と内容を決定する設定が保持されます。</span><span class="sxs-lookup"><span data-stu-id="e6737-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="e6737-104">この手順に従う前に、トレースが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6737-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="e6737-105">トレースの有効化については、「[ネットワークのトレースの有効化](enabling-network-tracing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6737-105">For information about enabling tracing, see [Enabling Network Tracing](enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="e6737-106">コンピューター構成ファイルの machine.config は、Windows をインストールしたディレクトリの %Windir%\Microsoft.NET\Framework フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e6737-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="e6737-107">コンピューターにインストールされた .NET Framework のバージョンごとに、%Windir%\Microsoft.NET\Framework の下のフォルダーに別々の machine.config ファイルがあります (例: C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config または C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config)。</span><span class="sxs-lookup"><span data-stu-id="e6737-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="e6737-108">これらの設定は、コンピューター構成ファイルよりも優先されるアプリケーション構成ファイルでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e6737-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="e6737-109">ネットワークのトレースを構成するには</span><span class="sxs-lookup"><span data-stu-id="e6737-109">To configure network tracing</span></span>  
  
- <span data-ttu-id="e6737-110">適切な構成ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="e6737-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="e6737-111">これらの設定の値とオプションを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e6737-111">The values and options for these settings are described in the tables below.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="System.Net" tracemode="includehex" maxdatasize="1024">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Cache">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Http">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Sockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.WebSockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="System.Net" value="Verbose"/>  
          <add name="System.Net.Cache" value="Verbose"/>  
          <add name="System.Net.Http" value="Verbose"/>  
          <add name="System.Net.Sockets" value="Verbose"/>  
          <add name="System.Net.WebSockets" value="Verbose"/>  
        </switches>  
        <sharedListeners>  
          <add name="System.Net"  
            type="System.Diagnostics.TextWriterTraceListener"  
            initializeData="network.log"
            traceOutputOptions="ProcessId, DateTime" 
          />  
        </sharedListeners>  
        <trace autoflush="true"/>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
 <span data-ttu-id="e6737-112">`<switches>` ブロックに名前を追加すると、トレース出力にその名前に関連する一部のメソッドからの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6737-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="e6737-113">次の表に出力を示します。</span><span class="sxs-lookup"><span data-stu-id="e6737-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="e6737-114">name</span><span class="sxs-lookup"><span data-stu-id="e6737-114">Name</span></span>|<span data-ttu-id="e6737-115">出力元</span><span class="sxs-lookup"><span data-stu-id="e6737-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="e6737-116"><xref:System.Net.Sockets.Socket>、<xref:System.Net.Sockets.TcpListener>、<xref:System.Net.Sockets.TcpClient>、および <xref:System.Net.Dns> クラスの一部のパブリック メソッド。</span><span class="sxs-lookup"><span data-stu-id="e6737-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="e6737-117"><xref:System.Net.HttpWebRequest>、<xref:System.Net.HttpWebResponse>、<xref:System.Net.FtpWebRequest>、および <xref:System.Net.FtpWebResponse> クラスの一部のパブリック メソッド、および SSL デバッグ情報 (無効な証明書、不足している発行元一覧、およびクライアント証明書エラー)。</span><span class="sxs-lookup"><span data-stu-id="e6737-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="e6737-118"><xref:System.Net.HttpListener>、<xref:System.Net.HttpListenerRequest>、および <xref:System.Net.HttpListenerResponse> クラスの一部のパブリック メソッド。</span><span class="sxs-lookup"><span data-stu-id="e6737-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="e6737-119">`System.Net.Cache` 内の一部のプライベート メソッドと内部メソッド。</span><span class="sxs-lookup"><span data-stu-id="e6737-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="e6737-120"><xref:System.Net.Http.HttpClient>、<xref:System.Net.Http.DelegatingHandler>、<xref:System.Net.Http.HttpClientHandler>、<xref:System.Net.Http.HttpMessageHandler>、<xref:System.Net.Http.MessageProcessingHandler>、および <xref:System.Net.Http.WebRequestHandler> クラスの一部のパブリック メソッド。</span><span class="sxs-lookup"><span data-stu-id="e6737-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="e6737-121"><xref:System.Net.WebSockets.ClientWebSocket> および <xref:System.Net.WebSockets.WebSocket> クラスの一部のパブリック メソッド。</span><span class="sxs-lookup"><span data-stu-id="e6737-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="e6737-122">次の表に示した属性で、トレース出力の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="e6737-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="e6737-123">属性名</span><span class="sxs-lookup"><span data-stu-id="e6737-123">Attribute name</span></span>|<span data-ttu-id="e6737-124">属性値</span><span class="sxs-lookup"><span data-stu-id="e6737-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="e6737-125">必須の <xref:System.String> 属性です。</span><span class="sxs-lookup"><span data-stu-id="e6737-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="e6737-126">出力の詳細度を設定します。</span><span class="sxs-lookup"><span data-stu-id="e6737-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="e6737-127">有効な値は、`Critical`、`Error`、`Verbose`、`Warning`、および `Information` です。</span><span class="sxs-lookup"><span data-stu-id="e6737-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="e6737-128">この属性は、この例に示すように、\<switches> 要素の \<add name> 要素で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6737-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="e6737-129">この属性を \<source> 要素で設定すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e6737-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="e6737-130">省略可能な <xref:System.Int32> 属性です。</span><span class="sxs-lookup"><span data-stu-id="e6737-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="e6737-131">各行トレースに含まれるネットワーク データの最大バイト数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e6737-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="e6737-132">既定値は 1024 です。</span><span class="sxs-lookup"><span data-stu-id="e6737-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="e6737-133">この属性は、この例に示すように、\<source> 要素で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6737-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="e6737-134">この属性を \<switches> 要素の下の要素で設定すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e6737-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="e6737-135">省略可能な <xref:System.String> 属性です。</span><span class="sxs-lookup"><span data-stu-id="e6737-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="e6737-136">プロトコル トレースを 16 進数およびテキストの形式で表示するには、`includehex` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6737-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="e6737-137">テキストのみを表示するには、`protocolonly` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6737-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="e6737-138">既定値は `includehex` です。</span><span class="sxs-lookup"><span data-stu-id="e6737-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="e6737-139">この属性は、この例に示すように、\<switches> 要素で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6737-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="e6737-140">この属性を \<source> 要素の下の要素で設定すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e6737-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6737-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6737-141">See also</span></span>

- [<span data-ttu-id="e6737-142">ネットワークのトレースの解釈</span><span class="sxs-lookup"><span data-stu-id="e6737-142">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="e6737-143">.NET Framework のネットワークのトレース</span><span class="sxs-lookup"><span data-stu-id="e6737-143">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="e6737-144">ネットワークのトレースの有効化</span><span class="sxs-lookup"><span data-stu-id="e6737-144">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="e6737-145">アプリケーションのトレースとインストルメント</span><span class="sxs-lookup"><span data-stu-id="e6737-145">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)
