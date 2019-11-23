---
title: インターフェイス定義言語-WCF 開発者向け gRPC
description: プロトコルバッファー IDL の概要を紹介します。
ms.date: 09/02/2019
ms.openlocfilehash: 1f304502bd0091f753a3d2f7854298f4bbf983f1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967625"
---
# <a name="interface-definition-language"></a><span data-ttu-id="37684-103">インターフェイス定義言語</span><span class="sxs-lookup"><span data-stu-id="37684-103">Interface Definition Language</span></span>

<span data-ttu-id="37684-104">WCF では、サービスは Web サービス定義言語 (WSDL) を使用して記述メタデータを公開できます。 WSDL は、実行時に .NET リフレクションを使用して動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="37684-104">With WCF, services can expose description metadata using the Web Service Definition Language (WSDL), which is generated dynamically using .NET Reflection at runtime.</span></span> <span data-ttu-id="37684-105">開発者は、このメタデータを使用して、これらのサービスのクライアントを生成できます。 SOAP over HTTP などのプラットフォームに依存しないバインディングが使用されている場合は、他の言語のクライアントを生成できます。</span><span class="sxs-lookup"><span data-stu-id="37684-105">Developers can use this metadata to generate clients for those services, potentially in other languages if a platform-neutral binding such as SOAP over HTTP is used.</span></span>

<span data-ttu-id="37684-106">gRPC は、プロトコルバッファーからインターフェイス定義言語 (IDL) を使用します。</span><span class="sxs-lookup"><span data-stu-id="37684-106">gRPC uses the Interface Definition Language (IDL) from Protocol Buffers.</span></span> <span data-ttu-id="37684-107">プロトコルバッファー IDL は、オープンな仕様を持つ、プラットフォームに依存しないカスタム言語です。</span><span class="sxs-lookup"><span data-stu-id="37684-107">The Protocol Buffers IDL is a custom, platform-neutral language with an open specification.</span></span> <span data-ttu-id="37684-108">開発者は、サービスを入力および出力と共に記述するために、ファイルを手動でコーディング `.proto` ます。</span><span class="sxs-lookup"><span data-stu-id="37684-108">Developers hand-code `.proto` files to describe services along with their inputs and outputs.</span></span> <span data-ttu-id="37684-109">これらの `.proto` ファイルを使用して、クライアントとサーバーの言語またはプラットフォーム固有のスタブを生成し、複数の異なるプラットフォームが通信できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="37684-109">These `.proto` files can then be used to generate language- or platform-specific stubs for clients and servers, allowing multiple different platforms to communicate.</span></span> <span data-ttu-id="37684-110">`.proto` ファイルを共有することにより、コードの依存関係を取らずに、他のサービスを使用するコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="37684-110">By sharing `.proto` files, teams can generate code to use each others' services without needing to take a code dependency.</span></span>

<span data-ttu-id="37684-111">Protobuf IDL の利点の1つは、カスタム言語として、gRPC を完全な言語とプラットフォームに依存しないようにすることです。これにより、他のテクノロジを優先することはできません。</span><span class="sxs-lookup"><span data-stu-id="37684-111">One of the advantages of the Protobuf IDL is that as a custom language it enables gRPC to be completely language and platform agnostic, not favoring any technology over another.</span></span>

<span data-ttu-id="37684-112">Protobuf IDL は、人間が読み取りと書き込みの両方を行うように設計されています。一方、WSDL は、機械で読み取り可能な形式であることを意図しています。</span><span class="sxs-lookup"><span data-stu-id="37684-112">The Protobuf IDL is also designed for humans to both read and write, whereas WSDL is intended as a machine-readable/writable format.</span></span> <span data-ttu-id="37684-113">通常、WCF サービスの WSDL を変更するには、サービスを実行し、サーバーから WSDL ファイルを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37684-113">Changing the WSDL of a WCF service typically requires making the changes to the service code itself, running the service and regenerating the WSDL file from the server.</span></span> <span data-ttu-id="37684-114">これに対し、`.proto` ファイルでは、変更をテキストエディターで簡単に適用し、生成されたコードを自動的にフローすることができます。</span><span class="sxs-lookup"><span data-stu-id="37684-114">By contrast, with a `.proto` file, changes are simple to apply with a text editor, and automatically flow through the generated code.</span></span> <span data-ttu-id="37684-115">Visual Studio 2019 では、保存時に `.proto` ファイルがバックグラウンドでビルドされます。VS Code などの他のエディターを使用する場合は、プロジェクトのビルド時に変更が適用されます。</span><span class="sxs-lookup"><span data-stu-id="37684-115">Visual Studio 2019 builds `.proto` files in the background when they are saved; when using other editors such as VS Code the changes will be applied when the project is built.</span></span>

<span data-ttu-id="37684-116">XML (特に SOAP) と比較すると、Protobuf を使用してエンコードされたメッセージには多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="37684-116">When compared with XML, and particularly SOAP, messages encoded using Protobuf have many advantages.</span></span> <span data-ttu-id="37684-117">Protobuf メッセージは、SOAP XML としてシリアル化されるのと同じデータよりも小さくなる傾向があります。また、エンコード、デコード、ネットワーク経由での転送が高速になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37684-117">Protobuf messages tend to be smaller than the same data serialized as SOAP XML, and encoding, decoding and transmitting them over a network can be faster.</span></span>

<span data-ttu-id="37684-118">SOAP と比較した場合の Protobuf の潜在的な欠点は、メッセージが人間が判読できないため、メッセージの内容をデバッグするために追加のツールが必要になることです。</span><span class="sxs-lookup"><span data-stu-id="37684-118">The potential disadvantage of Protobuf compared to SOAP is that, because the messages are not human readable, additional tooling is required to debug message content.</span></span>

> [!TIP]
> <span data-ttu-id="37684-119">gRPC*は*、プリコンパイルされたスタブを使用せずに動的にサービスにアクセスするためのサーバーリフレクションをサポートしています。ただし、アプリケーション固有のクライアントよりも汎用ツールの方が適しています。</span><span class="sxs-lookup"><span data-stu-id="37684-119">gRPC *does* support server reflection for dynamically accessing services without pre-compiled stubs, although it is intended more for general-purpose tools than application-specific clients.</span></span> <span data-ttu-id="37684-120">GRPC サーバーリフレクションの詳細については、GitHub の「 [grpc/grpc](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md)リポジトリ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37684-120">For more information about gRPC Server Reflection, see [grpc/grpc](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) repository on GitHub.</span></span>

> [!NOTE]
> <span data-ttu-id="37684-121">NetTCP バインドと共に使用される WCF のバイナリ形式は、コンパクトさもとパフォーマンスの点で Protobuf に非常に近いものですが、NetTCP は .NET クライアントとサーバーの間でのみ使用できます。一方、Protobuf はクロスプラットフォームソリューションです。</span><span class="sxs-lookup"><span data-stu-id="37684-121">WCF's binary format, used with the NetTCP binding, is much closer to Protobuf in terms of compactness and performance, but NetTCP is only usable between .NET clients and servers, whereas Protobuf is a cross-platform solution.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="37684-122">[前へ](approach.md)
>[次へ](network-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="37684-122">[Previous](approach.md)
[Next](network-protocols.md)</span></span>
