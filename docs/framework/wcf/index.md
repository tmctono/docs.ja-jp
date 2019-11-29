---
title: Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF]
- WCF [WCF]
ms.assetid: 149348a6-bf82-4ccc-9604-fa7cc88c0749
ms.openlocfilehash: 836913dd35d127d181c753341a7c39c453242a8f
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552681"
---
# <a name="develop-service-oriented-applications-with-wcf"></a><span data-ttu-id="ee54d-102">WCF を使用したサービス指向アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="ee54d-102">Develop Service-Oriented Applications with WCF</span></span>

<span data-ttu-id="ee54d-103">このセクションでは、サービス指向アプリケーションを構築するための統一プログラミング モデルを提供する Windows Communication Foundation (WCF) について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-103">This section of the documentation provides information about Windows Communication Foundation (WCF), which is a unified programming model for building service-oriented applications.</span></span> <span data-ttu-id="ee54d-104">これを使用して開発者は、プラットフォーム間を統合し、既存のコンポーネントと相互運用する、セキュリティで保護された信頼性の高いトランザクション型のソリューションを構築できます。</span><span class="sxs-lookup"><span data-stu-id="ee54d-104">It enables developers to build secure, reliable, transacted solutions that integrate across platforms and interoperate with existing investments.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ee54d-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ee54d-105">In this section</span></span>

 <span data-ttu-id="ee54d-106">[Windows Communication Foundation 4.5\ の新機能](whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-106">[What's New in Windows Communication Foundation 4.5](whats-new.md)\</span></span>
 <span data-ttu-id="ee54d-107">Windows Communication Foundation の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-107">Discusses features new to Windows Communication Foundation.</span></span>

 <span data-ttu-id="ee54d-108">[WCF の単純化機能](wcf-simplification-features.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-108">[WCF Simplification Features](wcf-simplification-features.md)</span></span>\
 <span data-ttu-id="ee54d-109">WCF アプリケーションの作成を容易にする新しい機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-109">Discusses new features that make writing WCF applications simpler.</span></span>

 <span data-ttu-id="ee54d-110">[ドキュメントのガイド](guide-to-the-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-110">[Guide to the Documentation](guide-to-the-documentation.md)</span></span>\
 <span data-ttu-id="ee54d-111">WCF ドキュメントの説明があります。</span><span class="sxs-lookup"><span data-stu-id="ee54d-111">A description of the WCF documentation</span></span>

 <span data-ttu-id="ee54d-112">[概念の概要](conceptual-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-112">[Conceptual Overview](conceptual-overview.md)</span></span>\
 <span data-ttu-id="ee54d-113">Windows Communication Foundation (WCF) メッセージング システムおよびその使用をサポートしているクラスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-113">Summarizes information about the Windows Communication Foundation (WCF) messaging system and the classes that support its use.</span></span>

 <span data-ttu-id="ee54d-114">[はじめにチュートリアル](getting-started-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-114">[Getting Started Tutorial](getting-started-tutorial.md)</span></span>\
 <span data-ttu-id="ee54d-115">WCF サービスとクライアントを作成する手順のチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="ee54d-115">A step by step tutorial to create a WCF service and client</span></span>

 <span data-ttu-id="ee54d-116">[基本的な WCF プログラミング](basic-wcf-programming.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-116">[Basic WCF Programming](basic-wcf-programming.md)</span></span>\
 <span data-ttu-id="ee54d-117">Windows Communication Foundation アプリケーションを作成するための基礎について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-117">Describes the fundamentals for creating Windows Communication Foundation applications.</span></span>

 <span data-ttu-id="ee54d-118">[WCF 機能の詳細](./feature-details/index.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-118">[WCF Feature Details](./feature-details/index.md)</span></span>\
 <span data-ttu-id="ee54d-119">使用する必要がある WCF 機能を選択するためのトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-119">Shows topics that let you choose which WCF feature or features you need to employ.</span></span>

 <span data-ttu-id="ee54d-120">[WCF](./extending/index.md)\ の拡張</span><span class="sxs-lookup"><span data-stu-id="ee54d-120">[Extending WCF](./extending/index.md)\</span></span>
 <span data-ttu-id="ee54d-121">WCF ランタイム コンポーネントを変更および拡張する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-121">Describes how to modify and extend WCF runtime components</span></span>

 <span data-ttu-id="ee54d-122">[ガイドラインとベストプラクティス](guidelines-and-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-122">[Guidelines and Best Practices](guidelines-and-best-practices.md)</span></span>\
 <span data-ttu-id="ee54d-123">Windows Communication Foundation (WCF) アプリケーションの作成のガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-123">Provides guidelines for creating Windows Communication Foundation (WCF) applications.</span></span>

 <span data-ttu-id="ee54d-124">[管理と診断の](./diagnostics/index.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-124">[Administration and Diagnostics](./diagnostics/index.md)</span></span>\
 <span data-ttu-id="ee54d-125">WCF の診断機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-125">Describes the diagnostic features of WCF</span></span>

 <span data-ttu-id="ee54d-126">[WCF\ に必要なオペレーティングシステムリソース](operating-system-resources-required-by-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-126">[Operating System Resources Required by WCF](operating-system-resources-required-by-wcf.md)\</span></span>
 <span data-ttu-id="ee54d-127">WCF に必要なオペレーティング システム リソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-127">Describes operating system resources required by WCF</span></span>

 <span data-ttu-id="ee54d-128">[セットアップに関する問題のトラブルシューティング](troubleshooting-setup-issues.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-128">[Troubleshooting Setup Issues](troubleshooting-setup-issues.md)</span></span>\
 <span data-ttu-id="ee54d-129">WCF のセットアップの問題に対処するためのガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-129">Provides guidance for fixing WCF setup issues</span></span>

 <span data-ttu-id="ee54d-130">[.Net リモート処理から WCF\ への移行](migrating-from-net-remoting-to-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-130">[Migrating from .NET Remoting to WCF](migrating-from-net-remoting-to-wcf.md)\</span></span>
 <span data-ttu-id="ee54d-131">.NET リモート処理と WCF を比較し、一般的なシナリオ用の移行のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-131">Compares .NET Remoting to WCF and provides migration guidance for common scenarios.</span></span>

 <span data-ttu-id="ee54d-132">[WCF 開発ツールの使用](using-the-wcf-development-tools.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-132">[Using the WCF Development Tools](using-the-wcf-development-tools.md)</span></span>\
 <span data-ttu-id="ee54d-133">WCFservice の開発に役立つ Visual Studio Windows Communication Foundation 開発ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-133">Describes the Visual Studio Windows Communication Foundation development tools that can assist you in developing your WCFservice.</span></span>

 <span data-ttu-id="ee54d-134">[Windows Communication Foundation ツール](tools.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-134">[Windows Communication Foundation Tools](tools.md)</span></span>\
 <span data-ttu-id="ee54d-135">WCF アプリケーションの作成、展開、および管理を簡単に行えるように設計されている WCF ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-135">Describes WCF tools designed to make it easier to create, deploy, and manage WCF applications</span></span>

 <span data-ttu-id="ee54d-136">[Windows Communication Foundation サンプル](./samples/index.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-136">[Windows Communication Foundation Samples](./samples/index.md)</span></span>\
 <span data-ttu-id="ee54d-137">Windows Communication Foundation のさまざまな特性について説明するサンプルがあります。</span><span class="sxs-lookup"><span data-stu-id="ee54d-137">Samples that provide instruction on various aspects of Windows Communication Foundation</span></span>

 <span data-ttu-id="ee54d-138">[Windows Communication Foundation 用語集](glossary.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-138">[Windows Communication Foundation Glossary](glossary.md)</span></span>\
 <span data-ttu-id="ee54d-139">WCF に固有の用語の一覧を表示します</span><span class="sxs-lookup"><span data-stu-id="ee54d-139">Shows a list of terms specific to WCF</span></span>

 <span data-ttu-id="ee54d-140">[一般的なリファレンス](general-reference.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-140">[General Reference](general-reference.md)</span></span>\
 <span data-ttu-id="ee54d-141">このセクションでは、Windows Communication Foundation のクライアントおよびサービスの設定に使用される要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54d-141">The section describes the elements that are used to configure Windows Communication Foundation clients and services.</span></span>

 <span data-ttu-id="ee54d-142">[プライバシー情報](privacy-information.md)</span><span class="sxs-lookup"><span data-stu-id="ee54d-142">[Privacy Information](privacy-information.md)</span></span>\
 <span data-ttu-id="ee54d-143">WCF とプライバシーに関する情報があります。</span><span class="sxs-lookup"><span data-stu-id="ee54d-143">Information regarding WCF and Privacy</span></span>
