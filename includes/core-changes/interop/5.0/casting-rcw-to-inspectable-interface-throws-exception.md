---
ms.openlocfilehash: 8693c1fdef5fa194b16127d4f1dd87e23ad68f2d
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438030"
---
### <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a><span data-ttu-id="2de62-101">RCW を `InterfaceIsIInspectable` インターフェイスにキャストすると、PlatformNotSupportedException がスローされる</span><span class="sxs-lookup"><span data-stu-id="2de62-101">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>

<span data-ttu-id="2de62-102">ランタイム呼び出し可能ラッパー (RCW) を <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> とマークされたインターフェイスにキャストすると、<xref:System.PlatformNotSupportedException> がスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2de62-102">Casting a runtime callable wrapper (RCW) to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> now throws a <xref:System.PlatformNotSupportedException>.</span></span> <span data-ttu-id="2de62-103">この変更は、[WinRT のサポートが .NET から削除された](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net)ことのフォローアップです。</span><span class="sxs-lookup"><span data-stu-id="2de62-103">This change is a follow up to the [removal of WinRT support from .NET](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2de62-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="2de62-104">Version introduced</span></span>

<span data-ttu-id="2de62-105">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="2de62-105">5.0 RC2</span></span>

#### <a name="change-description"></a><span data-ttu-id="2de62-106">変更内容</span><span class="sxs-lookup"><span data-stu-id="2de62-106">Change description</span></span>

<span data-ttu-id="2de62-107">.NET 5.0 Preview 6 以前の .NET バージョンでは、RCW を <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> とマークされたインターフェイスにキャストすると想定どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="2de62-107">In .NET versions prior to .NET 5.0 preview 6, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> works as expected.</span></span> <span data-ttu-id="2de62-108">.NET 5.0 Preview 6-8 および RC1 では、RCW を <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> インターフェイスに正常にキャストできます。</span><span class="sxs-lookup"><span data-stu-id="2de62-108">In .NET 5.0 previews 6-8 and RC1, you can successfully cast an RCW to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface.</span></span> <span data-ttu-id="2de62-109">ただし、ランタイムの基になるサポートが [.NET 5.0 Preview 6 で削除された](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net)ため、インターフェイスでメソッドを実行するとアクセス違反が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2de62-109">However, you might get access violations when you execute methods on the interface, because the underlying support in the runtime [was removed in .NET 5.0 preview 6](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span>

<span data-ttu-id="2de62-110">.NET 5.0 RC2 以降のバージョンでは、RCW を <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> とマークされたインターフェイスにキャストすると、キャスト時に <xref:System.PlatformNotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2de62-110">In .NET 5.0 RC2 and later versions, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> throws a <xref:System.PlatformNotSupportedException> at cast time.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2de62-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="2de62-111">Reason for change</span></span>

<span data-ttu-id="2de62-112"><xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> のサポートが、[前の .NET 5.0 Preview で削除されました](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net)。</span><span class="sxs-lookup"><span data-stu-id="2de62-112">The support for <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> was [removed in a previous .NET 5.0 preview](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span> <span data-ttu-id="2de62-113">しかし、<xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> インターフェイスへのキャストが誤って見落とされました。</span><span class="sxs-lookup"><span data-stu-id="2de62-113">However, casting to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface was accidentally overlooked.</span></span> <span data-ttu-id="2de62-114">ランタイムの基になるサポートが存在しなくなったため、<xref:System.PlatformNotSupportedException> をスローすると、正常なエラー パスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="2de62-114">Since the underlying support in the runtime no longer exists, throwing a <xref:System.PlatformNotSupportedException> enables a graceful failure path.</span></span> <span data-ttu-id="2de62-115">また、例外をスローすることで、この機能がサポートされなくなったことが見つけやすくなります。</span><span class="sxs-lookup"><span data-stu-id="2de62-115">Throwing an exception also makes it more discoverable that this feature is no longer supported.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2de62-116">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="2de62-116">Recommended action</span></span>

- <span data-ttu-id="2de62-117">Windows ランタイムメタデータ (WinMD) ファイルでインターフェイスを定義できる場合は、代わりに C#/WinRT ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="2de62-117">If you can define the interface in a Windows runtime metadata (WinMD) file, use the C#/WinRT tool instead.</span></span>

- <span data-ttu-id="2de62-118">それ以外の場合は、<xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> ではなく <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> としてインターフェイスをマークし、<xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> メソッドのインターフェイスの先頭に 3 つのダミー エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="2de62-118">Otherwise, mark the interface as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> instead of <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, and add three dummy entries to the start of the interface for the <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> methods.</span></span> <span data-ttu-id="2de62-119">次のコード スニペットに例を示します。</span><span class="sxs-lookup"><span data-stu-id="2de62-119">The following code snippet shows an example.</span></span>

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

#### <a name="category"></a><span data-ttu-id="2de62-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="2de62-120">Category</span></span>

<span data-ttu-id="2de62-121">Interop</span><span class="sxs-lookup"><span data-stu-id="2de62-121">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2de62-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2de62-122">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

-->
