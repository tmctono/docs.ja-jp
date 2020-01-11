---
title: 分析トレースの概要
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: 7718c8f2a82178bedc080eda0cd0fdf728213a27
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900638"
---
# <a name="analytic-tracing-overview"></a><span data-ttu-id="0657f-102">分析トレースの概要</span><span class="sxs-lookup"><span data-stu-id="0657f-102">Analytic tracing overview</span></span>

<span data-ttu-id="0657f-103">[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] の分析トレースは、Event Tracing for Windows (ETW) を基盤とするトレース機能のセットです。詳細度は低いのですが、パフォーマンスに優れています。</span><span class="sxs-lookup"><span data-stu-id="0657f-103">Analytic tracing in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] is a high performance and low verbosity tracing feature set on top of Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="0657f-104">ETW は、カーネル レベルで実行され、トレース操作のオーバーヘッドを大幅に削減します。</span><span class="sxs-lookup"><span data-stu-id="0657f-104">ETW runs at the kernel-level to greatly reduce the overhead of tracing operations.</span></span> <span data-ttu-id="0657f-105">ユーザー モードおよびカーネル モードのイベントを効率よくバッファーし、サービスの再起動を必要とすることなく、動的にログを有効化できます。</span><span class="sxs-lookup"><span data-stu-id="0657f-105">It efficiently buffers user- and kernel-mode events, and allows dynamic enabling of logging without requiring service restarts.</span></span> <span data-ttu-id="0657f-106">トレース データは、生成および受信されると、イベント ログから確認できます。</span><span class="sxs-lookup"><span data-stu-id="0657f-106">The tracing data is available in the event logs after it has been emitted and received.</span></span>

<span data-ttu-id="0657f-107">ETW の詳細については、「 [etw を使用したデバッグとパフォーマンスチューニングの向上](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0657f-107">For more information about ETW, see [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).</span></span>

 <span data-ttu-id="0657f-108">Windows システム、セキュリティ、およびアプリケーションのイベントログを使用してアプリケーションを分析するだけでなく、Windows Vista および Windows Server 2008 では、[アプリケーションとサービスログ] の最上位ノードに追加のログが導入されました。</span><span class="sxs-lookup"><span data-stu-id="0657f-108">In addition to using the Windows System, Security, and Application event logs to analyze application, Windows Vista and Windows Server 2008 introduced additional logs under the Applications and Services Logs top-level node.</span></span> <span data-ttu-id="0657f-109">これらの新しいログは、システム全体に影響するグローバルなイベント (セキュリティ イベント ログで記録されるようなイベントなど) ではなく、特定のアプリケーションやコンポーネントのイベントを格納することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="0657f-109">The purpose of these new logs is to store events for a particular application or specific component instead of global events that have a system-wide impact (such as the type of events that the Security event log might record).</span></span> [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] <span data-ttu-id="0657f-110">は、WCF トレースイベント、WCF メッセージログ、および [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] 追跡レコードのログ記録を、アプリケーションとサービスログに統合して関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0657f-110">unifies and correlates the logging of WCF Trace Events, WCF Message Logs, and [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] Tracking records to the Applications and Services Logs.</span></span>

<span data-ttu-id="0657f-111">以下のセクションでは、WCF 分析トレースに適用される概念と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="0657f-111">The following sections cover concepts and capabilities that apply to WCF analytic tracing.</span></span>

## <a name="enable-wcf-diagnostics-settings"></a><span data-ttu-id="0657f-112">WCF 診断設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="0657f-112">Enable WCF Diagnostics Settings</span></span>

<span data-ttu-id="0657f-113">WCF 診断は、`<system.serviceModel><diagnostics>` 構成セクション内で有効になります。</span><span class="sxs-lookup"><span data-stu-id="0657f-113">WCF diagnostics are enabled within the `<system.serviceModel><diagnostics>` configuration section.</span></span>

```xml
<system.serviceModel>
  <diagnostics>
```

<span data-ttu-id="0657f-114">Web でホストされる IIS 仮想アプリケーションの WCF 診断設定は、web.config*ファイルで*有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0657f-114">WCF diagnostic settings for a Web-hosted IIS virtual application are enabled in its *Web.config* file.</span></span> <span data-ttu-id="0657f-115">もう1つの方法は、アプリケーション内のサブディレクトリに*web.config ファイルを*作成することです。</span><span class="sxs-lookup"><span data-stu-id="0657f-115">Another option is to create a *Web.config* file in a subdirectory within the application.</span></span> <span data-ttu-id="0657f-116">このオプションを選択すると、サブディレクトリ内のすべてのサービスに設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0657f-116">This choice applies the settings to all of the services within a subdirectory.</span></span> <span data-ttu-id="0657f-117">診断設定がアプリケーション内のすべてのサービスに対して一貫して初期化されるようにするには、アプリケーション内の個々のサブディレクトリの1つではなく、アプリケーションディレクトリ内の*web.config ファイル内*に設定を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0657f-117">To ensure that the diagnostics settings are initialized consistently for all services within the application, the settings should be within the *Web.config* file in the application directory and not in one of the individual subdirectories within the application.</span></span>

## <a name="channels"></a><span data-ttu-id="0657f-118">チャネル</span><span class="sxs-lookup"><span data-stu-id="0657f-118">Channels</span></span>

<span data-ttu-id="0657f-119">ETW の場合、ソフトウェア コンポーネントは、チャネルを使用することで、トレース イベントをユーザーの種類に応じて振り分けることができます。</span><span class="sxs-lookup"><span data-stu-id="0657f-119">ETW allows software components to direct tracing events to a particular audience by use of channels.</span></span> <span data-ttu-id="0657f-120">たとえば、システム管理者のイベントを1つのチャネルに送信し、アプリケーション開発者にとって重要なイベントを別のチャネルに送信できます。</span><span class="sxs-lookup"><span data-stu-id="0657f-120">For example, you can send events for system administrators to one channel and events that application developers care about to another channel.</span></span> <span data-ttu-id="0657f-121">チャネルには名前が付けられ、Windows に登録されるため、コンシューマーはイベントビューアーを使用してチャネルのイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0657f-121">Channels are named and registered with Windows so that consumers can view a channel's events using Event Viewer.</span></span>

 <span data-ttu-id="0657f-122">[!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] の WCF の分析トレース機能は、Microsoft-Windows-アプリケーション-サーバーアプリケーションのチャネルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="0657f-122">The analytic tracing feature for WCF in [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] writes to the Microsoft-Windows-Application-Server-Applications channel.</span></span> <span data-ttu-id="0657f-123">このチャネルは、運用環境で WCF サービスの正常性を監視する必要があるユーザー向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="0657f-123">This channel is designed for users who want to monitor the health of WCF services in production.</span></span> <span data-ttu-id="0657f-124">多くの正常性の監視とトラブルシューティングのシナリオで使用できる少数のイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="0657f-124">It defines a small set of events that can be used in many health monitoring and troubleshooting scenarios.</span></span>

 <span data-ttu-id="0657f-125">メッセージがイベント ログで正常にデコードされるように Event Tracing for Windows マニファストを有効にするために、次のようにコマンド ラインで ServiceModelReg ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="0657f-125">To enable the Event Tracing for Windows manifest so that messages are decoded properly in the event log, use the ServiceModelReg tool on the command line as follows:</span></span>

 `ServiceModelReg.exe -i -c:etw`

## <a name="dynamic-configuration"></a><span data-ttu-id="0657f-126">動的構成</span><span class="sxs-lookup"><span data-stu-id="0657f-126">Dynamic Configuration</span></span>

<span data-ttu-id="0657f-127">ETW のインフラストラクチャでは、標準の Windows ツールを使用して動的にトレースを有効化および構成できます。</span><span class="sxs-lookup"><span data-stu-id="0657f-127">The ETW infrastructure allows tracing to be enabled and configured dynamically using standard Windows tools.</span></span> <span data-ttu-id="0657f-128">詳細については、「[分析トレースの動的な有効化](dynamically-enabling-analytic-tracing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0657f-128">For more information, see [Dynamically Enabling Analytic Tracing](dynamically-enabling-analytic-tracing.md).</span></span>

## <a name="message-flow-tracing"></a><span data-ttu-id="0657f-129">メッセージ フローのトレース</span><span class="sxs-lookup"><span data-stu-id="0657f-129">Message Flow Tracing</span></span>

<span data-ttu-id="0657f-130">メッセージフローのトレースを有効にする方法の詳細については、「[メッセージフローのトレースの構成](configuring-message-flow-tracing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0657f-130">For more information about how to enable message flow tracing, see [Configuring Message Flow Tracing](configuring-message-flow-tracing.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="0657f-131">キーワード</span><span class="sxs-lookup"><span data-stu-id="0657f-131">Keywords</span></span>

<span data-ttu-id="0657f-132">キーワードは、トレースメッセージをフィルター処理し、イベントを生成した .NET Framework のコンポーネントを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0657f-132">Keywords are used to filter trace messages and define which component of the .NET Framework emitted the event.</span></span> <span data-ttu-id="0657f-133">詳細については、「[分析トレースの動的な有効化](dynamically-enabling-analytic-tracing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0657f-133">For more information, see [Dynamically Enabling Analytic Tracing](dynamically-enabling-analytic-tracing.md).</span></span>
