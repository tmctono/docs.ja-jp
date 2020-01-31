---
title: プロファイル (アンマネージ API リファレンス)
ms.date: 03/30/2017
helpviewer_keywords:
- profiling [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], profiling
- unmanaged API reference [.NET Framework], profiling
ms.assetid: 14c68e84-657e-49c2-aa8b-4978dbaf4454
ms.openlocfilehash: 40c464a6070ad7fd4c21ad4ea366e907ca1e4a31
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868162"
---
# <a name="profiling-unmanaged-api-reference"></a><span data-ttu-id="7343e-102">プロファイル (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7343e-102">Profiling (Unmanaged API Reference)</span></span>

<span data-ttu-id="7343e-103">プロファイル API を使用することにより、プロファイラーは共通言語ランタイム (CLR) によるプログラムの実行を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="7343e-103">The profiling API enables a profiler to monitor a program's execution by the common language runtime (CLR).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7343e-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7343e-104">In This Section</span></span>

 <span data-ttu-id="7343e-105">[プロファイルの概要](profiling-overview.md) .NET Framework 環境でのプロファイルのサポートを目的として CLR によって提供されているサービスおよびインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7343e-105">[Profiling Overview](profiling-overview.md) Describes the services and interfaces that the CLR provides to support profiling in the .NET Framework environment.</span></span>

 <span data-ttu-id="7343e-106">[プロファイル インターフェイス](profiling-interfaces.md) プロファイル API で使用されるアンマネージド インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7343e-106">[Profiling Interfaces](profiling-interfaces.md) Describes the unmanaged interfaces that the profiling API uses.</span></span>

 <span data-ttu-id="7343e-107">[プロファイル環境変数の設定](setting-up-a-profiling-environment.md) .NET Framework アプリケーションをプロファイルする場合に行う必要がある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="7343e-107">[Setting Up a Profiling Environment](setting-up-a-profiling-environment.md) Describes the steps you must take to profile a .NET Framework application.</span></span>

 <span data-ttu-id="7343e-108">[CLR プロファイラーと Windows ストア アプリ](clr-profilers-and-windows-store-apps.md) CLR プロファイル API を使用することで Windows ストア アプリを正しく操作する診断ツールを移植する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7343e-108">[CLR Profilers and Windows Store Apps](clr-profilers-and-windows-store-apps.md) Discusses how to port diagnostic tools that consume the CLR Profiling API to work successfully with Windows Store apps.</span></span>

 <span data-ttu-id="7343e-109">[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md) メソッド呼び出しによって `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT が返される条件について説明します。</span><span class="sxs-lookup"><span data-stu-id="7343e-109">[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md) Documents the conditions under which a method call returns the `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span></span>

 <span data-ttu-id="7343e-110">[グローバル静的関数のプロファイル](profiling-global-static-functions.md) プロファイル API で使用されるアンマネージド グローバル静的関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="7343e-110">[Profiling Global Static Functions](profiling-global-static-functions.md) Describes the unmanaged global static functions that the profiling API uses.</span></span>

 <span data-ttu-id="7343e-111">[列挙型のプロファイリング](profiling-enumerations.md) プロファイル API で使用されるアンマネージド列挙型について説明します。</span><span class="sxs-lookup"><span data-stu-id="7343e-111">[Profiling Enumerations](profiling-enumerations.md) Describes the unmanaged enumerations that the profiling API uses.</span></span>

 <span data-ttu-id="7343e-112">[構造体のプロファイリング](profiling-structures.md) プロファイル API で使用されるアンマネージド構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="7343e-112">[Profiling Structures](profiling-structures.md) Describes the unmanaged structures that the profiling API uses.</span></span>
