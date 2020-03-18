---
title: ネイティブ相互運用性 - .NET
description: .Net のネイティブ コンポーネントとやり取りする方法を説明します。
ms.date: 01/18/2019
ms.openlocfilehash: 330466d74cc268214f74c4f575e6a2961f678972
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706336"
---
# <a name="native-interoperability"></a><span data-ttu-id="aa5ef-103">ネイティブ相互運用性</span><span class="sxs-lookup"><span data-stu-id="aa5ef-103">Native interoperability</span></span>

<span data-ttu-id="aa5ef-104">次の各記事では、.NET での "ネイティブ相互運用" のさまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-104">The following articles show the various ways of doing "native interoperability" in .NET.</span></span>

<span data-ttu-id="aa5ef-105">ネイティブ コードの呼び出しが必要になる理由としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-105">There are a few reasons why you'd want to call into native code:</span></span>

- <span data-ttu-id="aa5ef-106">オペレーティング システムに付属している大量の API が、マネージド クラス ライブラリに存在していない。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-106">Operating systems come with a large volume of APIs that aren't present in the managed class libraries.</span></span> <span data-ttu-id="aa5ef-107">この主な例には、ハードウェアやオペレーティング システムの管理機能へのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-107">A prime example for this scenario would be access to hardware or operating system management functions.</span></span>
- <span data-ttu-id="aa5ef-108">C スタイル ABI (ネイティブ ABI) を持つか生成できる他のコンポーネントと通信する。たとえば、[Java ネイティブ インターフェイス (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) を介して公開されている Java コードや、ネイティブ コンポーネントを生成できるその他のマネージド言語です。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-108">Communicating with other components that have or can produce C-style ABIs (native ABIs), such as Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
- <span data-ttu-id="aa5ef-109">Windows では、インストールされるソフトウェアのほとんどが (たとえば Microsoft Office スイート)、COM コンポーネントを登録します。このコンポーネントは、そのソフトウェアのプログラムを表すものであり、開発者による自動化や使用が可能になります。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-109">On Windows, most of the software that gets installed, such as the Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="aa5ef-110">これも、ネイティブ相互運用性を必要とします。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-110">This also requires native interoperability.</span></span>

<span data-ttu-id="aa5ef-111">開発者がネイティブ コンポーネントとやり取りすることが必要になる状況やシナリオは、上記の一覧に示すものがすべてではありません。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-111">The previous list doesn't cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="aa5ef-112">たとえば、.NET クラス ライブラリは、ネイティブ相互運用性サポートを使用して、コンソールのサポートと操作、ファイル システムのアクセスなど、そのかなりの数の API を実装しています。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-112">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="aa5ef-113">ただし、必要であればできる、ということを覚えておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-113">However, it's important to note that there's an option if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="aa5ef-114">このセクションのほとんどの例は、.NET Core でサポートされる 3 つのプラットフォームすべて (Windows、Linux、macOS) について提示しています。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-114">Most of the examples in this section will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="aa5ef-115">ただし、短い解説的な例については、Windows ファイル名と拡張子 (つまり、ライブラリの場合は "dll") を使用する 1 つのサンプルだけを示します。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-115">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="aa5ef-116">その機能が Linux や macOS で使用できないというわけではなく、単に便宜上のためにそうしています。</span><span class="sxs-lookup"><span data-stu-id="aa5ef-116">This doesn't mean that those features aren't available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa5ef-117">参照</span><span class="sxs-lookup"><span data-stu-id="aa5ef-117">See also</span></span>

- [<span data-ttu-id="aa5ef-118">プラットフォーム呼び出し (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="aa5ef-118">Platform Invoke (P/Invoke)</span></span>](pinvoke.md)
- [<span data-ttu-id="aa5ef-119">型のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="aa5ef-119">Type marshaling</span></span>](type-marshaling.md)
- [<span data-ttu-id="aa5ef-120">ネイティブ相互運用性のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="aa5ef-120">Native interoperability best practices</span></span>](best-practices.md)
