---
title: UnsafeNclNativeMethods クラス (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 46756a0d1d69b4768dbb8dcdd7ab098d3f1849bf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990533"
---
# <a name="unsafenclnativemethods-class"></a><span data-ttu-id="c59e4-102">UnsafeNclNativeMethods クラス</span><span class="sxs-lookup"><span data-stu-id="c59e4-102">UnsafeNclNativeMethods class</span></span>

<span data-ttu-id="c59e4-103">Unsafe ネイティブネットワークメソッドをインポートするクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c59e4-103">Contains classes that import unsafe native networking methods.</span></span> <span data-ttu-id="c59e4-104">このクラスは継承できません。</span><span class="sxs-lookup"><span data-stu-id="c59e4-104">This class cannot be inherited.</span></span>

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> <span data-ttu-id="c59e4-105">このクラスは内部的なものであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="c59e4-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c59e4-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c59e4-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="nativepki-class"></a><span data-ttu-id="c59e4-107">Pipki クラス</span><span class="sxs-lookup"><span data-stu-id="c59e4-107">NativePKI class</span></span>

<span data-ttu-id="c59e4-108">crypt32.dll からインポートされたメソッドを格納します。</span><span class="sxs-lookup"><span data-stu-id="c59e4-108">Contains methods imported from crypt32.dll.</span></span> <span data-ttu-id="c59e4-109">これらのメソッドは、ハイパーテキスト転送プロトコルセキュア (HTTPS) を使用する場合に証明書を処理します。</span><span class="sxs-lookup"><span data-stu-id="c59e4-109">These methods handle certificates when using Hypertext Transfer Protocol Secure (HTTPS).</span></span> <span data-ttu-id="c59e4-110">このクラスは継承できません。</span><span class="sxs-lookup"><span data-stu-id="c59e4-110">This class cannot be inherited.</span></span>

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a><span data-ttu-id="c59e4-111">Pipki. FindClientCertificates メソッド</span><span class="sxs-lookup"><span data-stu-id="c59e4-111">NativePKI.FindClientCertificates method</span></span>

<span data-ttu-id="c59e4-112">サーバーに送信できる使用可能なクライアント証明書を検出します。</span><span class="sxs-lookup"><span data-stu-id="c59e4-112">Discovers available client certificates to send to the server.</span></span>

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a><span data-ttu-id="c59e4-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="c59e4-113">Return value</span></span>

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

<span data-ttu-id="c59e4-114">使用可能なクライアント証明書のコレクション。</span><span class="sxs-lookup"><span data-stu-id="c59e4-114">A collection of available client certificates.</span></span>

## <a name="requirements"></a><span data-ttu-id="c59e4-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="c59e4-115">Requirements</span></span>

<span data-ttu-id="c59e4-116">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c59e4-116">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c59e4-117">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="c59e4-117">**Assembly:** System (in System.dll)</span></span>
