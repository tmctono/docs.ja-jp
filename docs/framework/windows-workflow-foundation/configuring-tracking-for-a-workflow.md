---
title: ワークフローの追跡の構成
ms.date: 03/30/2017
ms.assetid: 905adcc9-30a0-4918-acd6-563f86db988a
ms.openlocfilehash: 97b25873e9f20d5d390b7a59531b3a5af32296df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802675"
---
# <a name="configuring-tracking-for-a-workflow"></a><span data-ttu-id="d310b-102">ワークフローの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="d310b-102">Configuring Tracking for a Workflow</span></span>

<span data-ttu-id="d310b-103">ワークフローは、次の 3 つの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="d310b-103">A workflow can execute in three ways:</span></span>

- <span data-ttu-id="d310b-104"><xref:System.ServiceModel.Activities.WorkflowServiceHost> でホストする</span><span class="sxs-lookup"><span data-stu-id="d310b-104">Hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>

- <span data-ttu-id="d310b-105"><xref:System.Activities.WorkflowApplication> として実行する</span><span class="sxs-lookup"><span data-stu-id="d310b-105">Executed as a <xref:System.Activities.WorkflowApplication></span></span>

- <span data-ttu-id="d310b-106"><xref:System.Activities.WorkflowInvoker> を使用して直接実行する</span><span class="sxs-lookup"><span data-stu-id="d310b-106">Executed directly using <xref:System.Activities.WorkflowInvoker></span></span>

<span data-ttu-id="d310b-107">ワークフローのホスト オプションに応じて、コードまたは構成ファイルによって追跡参加要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d310b-107">Depending on the workflow hosting option, a tracking participant can be added either through code or through a configuration file.</span></span> <span data-ttu-id="d310b-108">ここでは、追跡参加要素を <xref:System.Activities.WorkflowApplication> および <xref:System.ServiceModel.Activities.WorkflowServiceHost> に追加して追跡を構成する方法、および <xref:System.Activities.WorkflowInvoker> の使用時に追跡を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d310b-108">This topic describes how tracking is configured by adding a tracking participant to a <xref:System.Activities.WorkflowApplication> and to a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, and how to enable tracking when using <xref:System.Activities.WorkflowInvoker>.</span></span>

## <a name="configuring-workflow-application-tracking"></a><span data-ttu-id="d310b-109">ワークフロー アプリケーション追跡の構成</span><span class="sxs-lookup"><span data-stu-id="d310b-109">Configuring Workflow Application Tracking</span></span>

<span data-ttu-id="d310b-110">ワークフローは、<xref:System.Activities.WorkflowApplication> クラスを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="d310b-110">A workflow can run using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="d310b-111">ここで、追跡参加要素を [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ワークフロー ホストに追加することで、<xref:System.Activities.WorkflowApplication> ワークフロー アプリケーション用に追跡を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d310b-111">This topic demonstrates how tracking is configured for a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] workflow application by adding a tracking participant to the <xref:System.Activities.WorkflowApplication> workflow host.</span></span> <span data-ttu-id="d310b-112">この場合、ワークフローはワークフロー アプリケーションとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="d310b-112">In this case, the workflow runs as a workflow application.</span></span> <span data-ttu-id="d310b-113"><xref:System.Activities.WorkflowApplication> クラスを使用する自己ホスト型の .exe ファイルであるコードを介して (構成ファイルを使用せずに)、ワークフロー アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d310b-113">You configure a workflow application through code (rather than by using a configuration file), which is a self-hosted .exe file using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="d310b-114">追跡参加要素は <xref:System.Activities.WorkflowApplication> インスタンスの拡張として追加します。</span><span class="sxs-lookup"><span data-stu-id="d310b-114">The tracking participant is added as an extension to the <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="d310b-115">これを行うには、<xref:System.Activities.Tracking.TrackingParticipant> を WorkflowApplication インスタンスの拡張コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d310b-115">This is done by adding the <xref:System.Activities.Tracking.TrackingParticipant> to the extensions collection for the WorkflowApplication instance.</span></span>

<span data-ttu-id="d310b-116">ワークフロー アプリケーションの場合、次のコードのように <xref:System.Activities.Tracking.EtwTrackingParticipant> 動作拡張を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d310b-116">For a workflow application, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension as shown in the following code.</span></span>

```csharp
LogActivity activity = new LogActivity();

WorkflowApplication instance = new WorkflowApplication(activity);
EtwTrackingParticipant trackingParticipant =
    new EtwTrackingParticipant
{

        TrackingProfile = new TrackingProfile
           {
               Name = "SampleTrackingProfile",
               ActivityDefinitionId = "ProcessOrder",
               Queries = new WorkflowInstanceQuery
               {
                  States = { "*" }
              }
          }
       };
instance.Extensions.Add(trackingParticipant);
```

### <a name="configuring-workflow-service-tracking"></a><span data-ttu-id="d310b-117">ワークフロー サービス追跡の構成</span><span class="sxs-lookup"><span data-stu-id="d310b-117">Configuring Workflow Service Tracking</span></span>

<span data-ttu-id="d310b-118">ワークフローは、<xref:System.ServiceModel.Activities.WorkflowServiceHost> サービスホストでホストされている場合に、WCF サービスとして公開できます。</span><span class="sxs-lookup"><span data-stu-id="d310b-118">A workflow can be exposed as a WCF service when hosted in the <xref:System.ServiceModel.Activities.WorkflowServiceHost> service host.</span></span> <span data-ttu-id="d310b-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> は、ワークフロー ベースのサービスの .NET ServiceHost の特殊な実装です。</span><span class="sxs-lookup"><span data-stu-id="d310b-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> is a specialized .NET ServiceHost implementation for a workflow-based service.</span></span> <span data-ttu-id="d310b-120">ここでは、[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] で実行されている <xref:System.ServiceModel.Activities.WorkflowServiceHost> ワークフロー サービスの追跡を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d310b-120">This section explains how to configure tracking for a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow service running in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="d310b-121">Web.config ファイル (Web ホスト サービスの場合) または App.config ファイル (コンソール アプリケーションなどのスタンドアロン アプリケーションでホストされるサービスの場合) を介し、サービス動作を指定して構成するか、またはコードを介し、サービス ホスト用に <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> コレクションに追跡固有の動作を追加して構成できます。</span><span class="sxs-lookup"><span data-stu-id="d310b-121">It is configured through a Web.config file (for a Web-hosted service) or an App.config file (for a service hosted in a stand-alone application, such as a console application) by specifying a service behavior or through code by adding a tracking-specific behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection for the service host.</span></span>

<span data-ttu-id="d310b-122"><xref:System.ServiceModel.WorkflowServiceHost>でホストされているワークフローサービスでは、次の例に示すように、構成ファイルで <`behavior`> 要素を使用して <xref:System.Activities.Tracking.EtwTrackingParticipant> を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d310b-122">For a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>

```xml
<behaviors>
   <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
   </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="d310b-123">また、<xref:System.ServiceModel.WorkflowServiceHost> でホストされるワークフロー サービスの場合、コードを介して <xref:System.Activities.Tracking.EtwTrackingParticipant> 動作拡張を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d310b-123">Alternatively, for a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension through code.</span></span> <span data-ttu-id="d310b-124">カスタムの追跡参加要素を追加するには、次のコード例のように、新しい動作拡張を作成し、それを <xref:System.ServiceModel.ServiceHost> に追加します。</span><span class="sxs-lookup"><span data-stu-id="d310b-124">To add a custom tracking participant, create a new behavior extension and add it to the <xref:System.ServiceModel.ServiceHost> as shown in the following example code.</span></span>

> [!NOTE]
> <span data-ttu-id="d310b-125">カスタム追跡参加要素を追加するカスタム動作要素を作成する方法を示すサンプルコードを表示する場合は、[追跡](./samples/tracking.md)のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d310b-125">If you want to view sample code that shows how to create a custom behavior element that adds a custom tracking participant, refer to the [Tracking](./samples/tracking.md) samples.</span></span>

```csharp
ServiceHost svcHost = new ServiceHost(typeof(WorkflowService), new
                                 Uri("http://localhost:8001/Sample"));
EtwTrackingBehavior trackingBehavior =
    new EtwTrackingBehavior
    {
        ProfileName = "Sample Tracking Profile"
    };
svcHost.Description.Behaviors.Add(trackingBehavior);
svcHost.Open();
```

<span data-ttu-id="d310b-126">追跡参加要素は、動作の拡張としてワークフロー サービス ホストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d310b-126">The tracking participant is added to the workflow service host as an extension to the behavior.</span></span>

<span data-ttu-id="d310b-127">以下のサンプル コードは、構成ファイルから追跡プロファイルを読み取る方法の例です。</span><span class="sxs-lookup"><span data-stu-id="d310b-127">This sample code below shows how to read a tracking profile from configuration file.</span></span>

```csharp
TrackingProfile GetProfile(string profileName, string displayName)
        {
            TrackingProfile trackingProfile = null;
            TrackingSection trackingSection = (TrackingSection)WebConfigurationManager.GetSection("system.serviceModel/tracking");
            if (trackingSection == null)
            {
                return null;
            }

            profileName ??= "";

            //Find the profile with the specified profile name in the list of profile found in config
            var match = from p in new List<TrackingProfile>(trackingSection.TrackingProfiles)
                        where (p.Name == profileName) && ((p.ActivityDefinitionId == displayName) || (p.ActivityDefinitionId == "*"))
                        select p;

            if (match.Count() == 0)
            {
                //return an empty profile
                trackingProfile = new TrackingProfile()
                {
                    ActivityDefinitionId = displayName
                };

            }
            else
            {
                trackingProfile = match.First();
            }

            return trackingProfile;
```

<span data-ttu-id="d310b-128">このサンプル コードは、ワークフロー ホストに追跡プロファイルを追加する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="d310b-128">This sample code shows how to add a tracking profile to a workflow host.</span></span>

```csharp
WorkflowServiceHost workflowServiceHost = serviceHostBase as WorkflowServiceHost;
if (null != workflowServiceHost)
{
    string workflowDisplayName = workflowServiceHost.Activity.DisplayName;
    TrackingProfile trackingProfile = GetProfile(this.profileName, workflowDisplayName);
    workflowServiceHost.WorkflowExtensions.Add(()  => new EtwTrackingParticipant {
        TrackingProfile = trackingProfile
    });
 }
```

> [!NOTE]
> <span data-ttu-id="d310b-129">追跡プロファイルの詳細については、「[追跡プロファイル](tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d310b-129">For more information on tracking profiles, refer to [Tracking Profiles](tracking-profiles.md).</span></span>

### <a name="configuring-tracking-using-workflowinvoker"></a><span data-ttu-id="d310b-130">WorkflowInvoker を使用した追跡の構成</span><span class="sxs-lookup"><span data-stu-id="d310b-130">Configuring tracking using WorkflowInvoker</span></span>

<span data-ttu-id="d310b-131"><xref:System.Activities.WorkflowInvoker> を使用して実行するワークフローの追跡を構成するには、追跡プロバイダーを拡張として <xref:System.Activities.WorkflowInvoker> インスタンスに追加します。</span><span class="sxs-lookup"><span data-stu-id="d310b-131">To configure tracking for a workflow executed using <xref:System.Activities.WorkflowInvoker>, add the tracking provider as an extension to a <xref:System.Activities.WorkflowInvoker> instance.</span></span> <span data-ttu-id="d310b-132">次のコード例は、[カスタム追跡](./samples/custom-tracking.md)サンプルからのものです。</span><span class="sxs-lookup"><span data-stu-id="d310b-132">The following code example is from the [Custom Tracking](./samples/custom-tracking.md) sample.</span></span>

```csharp
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
invoker.Invoke();
```

### <a name="viewing-tracking-records-in-event-viewer"></a><span data-ttu-id="d310b-133">イベント ビューアーでの追跡レコードの表示</span><span class="sxs-lookup"><span data-stu-id="d310b-133">Viewing tracking records in Event Viewer</span></span>

<span data-ttu-id="d310b-134">WF 実行 - 分析ログとデバッグ ログ - を追跡すると、特に興味深い 2 つのイベント ビューアーのログ記録があります。</span><span class="sxs-lookup"><span data-stu-id="d310b-134">There are two Event Viewer logs of particular interest to view when tracking WF execution - the Analytic log and the Debug log.</span></span> <span data-ttu-id="d310b-135">どちらも [Microsoft&#124;Windows&#124;アプリケーションサーバー-アプリケーション] ノードの下に存在します。</span><span class="sxs-lookup"><span data-stu-id="d310b-135">Both reside under the Microsoft&#124;Windows&#124;Application Server-Applications node.</span></span> <span data-ttu-id="d310b-136">このセクション含まれるログは、システム全体に影響を及ぼすイベントではなく、1 つのアプリケーションからのイベントを格納します。</span><span class="sxs-lookup"><span data-stu-id="d310b-136">Logs within this section contain events from a single application rather than events that have an impact on the entire system.</span></span>

<span data-ttu-id="d310b-137">デバッグ トレースのイベントがデバッグ ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d310b-137">Debug trace events are written to the Debug Log.</span></span> <span data-ttu-id="d310b-138">イベント ビューアー内の WF のデバッグ トレース イベントを収集するには、デバッグ ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d310b-138">To collect WF debug trace events in the Event Viewer, enable the Debug Log.</span></span>

1. <span data-ttu-id="d310b-139">イベントビューアーを開くには、**スタート** をクリックし、実行 をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="d310b-139">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="d310b-140">[実行] ダイアログボックスで、「`eventvwr`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d310b-140">In the Run dialog, type `eventvwr`.</span></span>

2. <span data-ttu-id="d310b-141">イベントビューアー ダイアログで、**アプリケーションとサービスログ** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="d310b-141">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>

3. <span data-ttu-id="d310b-142">**[Microsoft]** 、 **[Windows]** 、 **[アプリケーションサーバー-アプリケーション]** ノードの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="d310b-142">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>

4. <span data-ttu-id="d310b-143">**[アプリケーションサーバー-アプリケーション]** ノードの下にある **[デバッグ]** ノードを右クリックし、 **[ログの有効化]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d310b-143">Right-click the **Debug** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>

5. <span data-ttu-id="d310b-144">トレースが有効になっているアプリケーションを実行して追跡イベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="d310b-144">Execute your tracing-enabled application to generate tracing events.</span></span>

6. <span data-ttu-id="d310b-145">**デバッグ** ノードを右クリックし、更新 を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="d310b-145">Right-click the **Debug** node and select **Refresh.**</span></span> <span data-ttu-id="d310b-146">トレース イベントが中央ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d310b-146">Tracing events should be visible in the center pane.</span></span>

<span data-ttu-id="d310b-147">WF 4 には、追跡レコードを ETW (Event Tracing for Windows) セッションに書き込む追跡参加要素が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d310b-147">WF 4 provides a tracking participant that writes tracking records to an ETW (Event Tracing for Windows) session.</span></span> <span data-ttu-id="d310b-148">ETW 追跡参加要素は、追跡レコードを定期受信するように追跡プロファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="d310b-148">The ETW tracking participant is configured with a tracking profile to subscribe to tracking records.</span></span> <span data-ttu-id="d310b-149">追跡が有効な場合は、エラーの追跡レコードが ETW に出力されます。</span><span class="sxs-lookup"><span data-stu-id="d310b-149">When tracking is enabled, errors tracking records are emitted to ETW.</span></span> <span data-ttu-id="d310b-150">ETW 追跡参加要素によって出力される追跡イベントに対応する ETW 追跡イベント (100 ～ 113 の範囲にある) が分析ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d310b-150">ETW tracking events (between the range of 100-113) corresponding to the tracking events emitted by the ETW tracking participant are written to the Analytic Log.</span></span>

<span data-ttu-id="d310b-151">追跡レコードを表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d310b-151">To view tracking records, follow these steps.</span></span>

1. <span data-ttu-id="d310b-152">イベントビューアーを開くには、**スタート** をクリックし、実行 をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="d310b-152">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="d310b-153">[実行] ダイアログボックスで、「`eventvwr`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d310b-153">In the Run dialog, type `eventvwr`.</span></span>

2. <span data-ttu-id="d310b-154">イベントビューアー ダイアログで、**アプリケーションとサービスログ** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="d310b-154">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>

3. <span data-ttu-id="d310b-155">**[Microsoft]** 、 **[Windows]** 、 **[アプリケーションサーバー-アプリケーション]** ノードの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="d310b-155">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>

4. <span data-ttu-id="d310b-156">**[アプリケーションサーバー-アプリケーション]** ノードの下の **[分析]** ノードを右クリックし、 **[ログの有効化]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d310b-156">Right-click the **Analytic** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>

5. <span data-ttu-id="d310b-157">追跡が有効になっているアプリケーションを実行して追跡レコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="d310b-157">Execute your tracking-enabled application to generate tracking records.</span></span>

6. <span data-ttu-id="d310b-158">**分析** ノードを右クリックし、更新 を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="d310b-158">Right-click the **Analytic** node and select **Refresh.**</span></span> <span data-ttu-id="d310b-159">追跡レコードが中央ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d310b-159">Tracking records should be visible in the center pane.</span></span>

<span data-ttu-id="d310b-160">次の図は、イベントビューアーでの追跡イベントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d310b-160">The following image shows tracking events in the event viewer:</span></span>

![追跡レコードを示すイベントビューアーのスクリーンショット。](./media/configuring-tracking-for-a-workflow/tracking-event-viewer.png)

### <a name="registering-an-application-specific-provider-id"></a><span data-ttu-id="d310b-162">アプリケーション固有のプロバイダー ID の登録</span><span class="sxs-lookup"><span data-stu-id="d310b-162">Registering an application-specific provider ID</span></span>

<span data-ttu-id="d310b-163">イベントを特定のアプリケーション ログに書き込む必要がある場合は、次の手順に従って新しいプロバイダー マニフェストを登録します。</span><span class="sxs-lookup"><span data-stu-id="d310b-163">If events need to be written to a specific application log, follow these steps to register the new provider manifest.</span></span>

1. <span data-ttu-id="d310b-164">アプリケーション構成ファイルでプロバイダー ID を宣言します。</span><span class="sxs-lookup"><span data-stu-id="d310b-164">Declare the provider ID in the application configuration file.</span></span>

    ```xml
    <system.serviceModel>
        <diagnostics etwProviderId="2720e974-9fe9-477a-bb60-81fe3bf91eec"/>
    </system.serviceModel>
    ```

2. <span data-ttu-id="d310b-165">マニフェストファイルを%windir%\Microsoft.NET\Framework\\\<最新バージョンの [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]> \Microsoft.Windows.ApplicationServer.Applications.man から一時的な場所にコピーし、名前を Applications_Provider1 ApplicationServer に変更します。</span><span class="sxs-lookup"><span data-stu-id="d310b-165">Copy the manifest file from %windir%\Microsoft.NET\Framework\\\<latest version of [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]>\Microsoft.Windows.ApplicationServer.Applications.man to a temporary location, and rename it to Microsoft.Windows.ApplicationServer.Applications_Provider1.man</span></span>

3. <span data-ttu-id="d310b-166">マニフェスト ファイルの GUID を新しい GUID に変更します。</span><span class="sxs-lookup"><span data-stu-id="d310b-166">Change the GUID in the manifest file to the new GUID.</span></span>

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"
    ```

4. <span data-ttu-id="d310b-167">既定のプロバイダーをアンインストールしない場合は、プロバイダー名を変更します。</span><span class="sxs-lookup"><span data-stu-id="d310b-167">Change the provider name if you do not want to uninstall the default provider.</span></span>

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"
    ```

5. <span data-ttu-id="d310b-168">前の手順でプロバイダー名を変更した場合は、マニフェスト ファイルのチャネル名を新しいプロバイダー名に変更します。</span><span class="sxs-lookup"><span data-stu-id="d310b-168">If you changed the provider name in the previous step, change the channel names in the manifest file to the new provider name.</span></span>

    ```xml
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Admin" chid="ADMIN_CHANNEL" symbol="ADMIN_CHANNEL" type="Admin" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ADMIN_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Operational" chid="OPERATIONAL_CHANNEL" symbol="OPERATIONAL_CHANNEL" type="Operational" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.OPERATIONAL_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Debug" chid="DEBUG_CHANNEL" symbol="DEBUG_CHANNEL" type="Debug" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.DEBUG_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Perf" chid="PERF_CHANNEL" symbol="PERF_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.PERF_CHANNEL.message)" />
    ```

6. <span data-ttu-id="d310b-169">次の手順に従ってリソース DLL を生成します。</span><span class="sxs-lookup"><span data-stu-id="d310b-169">Generate the resource DLL by following these steps.</span></span>

    1. <span data-ttu-id="d310b-170">Windows SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d310b-170">Install the Windows SDK.</span></span> <span data-ttu-id="d310b-171">Windows SDK には、メッセージコンパイラ ([mc](/windows/win32/wes/message-compiler--mc-exe-)) とリソースコンパイラ ([rc .exe](/windows/win32/menurc/using-rc-the-rc-command-line-)) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d310b-171">The Windows SDK includes the message compiler ([mc.exe](/windows/win32/wes/message-compiler--mc-exe-)) and resource compiler ([rc.exe](/windows/win32/menurc/using-rc-the-rc-command-line-)).</span></span>

    2. <span data-ttu-id="d310b-172">Windows SDK コマンド プロンプトで、新しいマニフェスト ファイルに対して mc.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="d310b-172">In a Windows SDK command prompt, run mc.exe on the new manifest file.</span></span>

        ```console
        mc.exe Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

    3. <span data-ttu-id="d310b-173">前の手順で生成されたリソース ファイルに対して rc.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="d310b-173">Run rc.exe on the resource file generated in the previous step.</span></span>

        ```console
        rc.exe  Microsoft.Windows.ApplicationServer.Applications_Provider1.rc
        ```

    4. <span data-ttu-id="d310b-174">NewProviderReg.cs という名前の空の cs ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d310b-174">Create an empty cs file called NewProviderReg.cs.</span></span>

    5. <span data-ttu-id="d310b-175">C# コンパイラを使用してリソース DLL を作成します。</span><span class="sxs-lookup"><span data-stu-id="d310b-175">Create a resource DLL using the C# compiler.</span></span>

        ```console
        csc /target:library /win32res:Microsoft.Windows.ApplicationServer.Applications_Provider1.res NewProviderReg.cs /out:Microsoft.Windows.ApplicationServer.Applications_Provider1.dll
        ```

    6. <span data-ttu-id="d310b-176">マニフェストファイルのリソースとメッセージ dll の名前を `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` から新しい dll 名に変更します。</span><span class="sxs-lookup"><span data-stu-id="d310b-176">Change the resource and message dll name in the manifest file from `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` to the new dll name.</span></span>

        ```xml
        <provider name="Microsoft-Windows-Application Server-Applications_Provider1" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" symbol="Microsoft_Windows_ApplicationServer_ApplicationEvents" resourceFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" messageFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll">
        ```

    7. <span data-ttu-id="d310b-177">[Wevtutil](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732848(v=ws.10))を使用してマニフェストを登録します。</span><span class="sxs-lookup"><span data-stu-id="d310b-177">Use [wevtutil](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732848(v=ws.10)) to register the manifest.</span></span>

        ```console
        wevtutil im Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

## <a name="see-also"></a><span data-ttu-id="d310b-178">参照</span><span class="sxs-lookup"><span data-stu-id="d310b-178">See also</span></span>

- <span data-ttu-id="d310b-179">[Windows Server App Fabric の監視](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d310b-179">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="d310b-180">[App Fabric を使用したアプリケーションの監視](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d310b-180">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
