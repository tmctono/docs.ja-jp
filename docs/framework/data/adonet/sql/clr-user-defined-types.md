---
title: CLR ユーザー定義型
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: 84d588e0c415daa7de19ea695c817f3eb24f732f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173589"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="17fa8-102">CLR ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="17fa8-102">CLR User-Defined Types</span></span>

<span data-ttu-id="17fa8-103">Microsoft SQL Server では、Microsoft .NET Framework 共通言語ランタイム (CLR) を使用して実装されるユーザー定義型 (UDT) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="17fa8-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="17fa8-104">CLR は SQL Server に統合されており、この機構を利用すると、データベースの型システムを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="17fa8-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="17fa8-105">UDT を利用すれば、SQL Server データ型システムのユーザー拡張が可能であり、複雑な構造化型を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="17fa8-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="17fa8-106">UDT は、アプリケーション アーキテクチャの観点から見て 2 つの重要な利点を備えています。</span><span class="sxs-lookup"><span data-stu-id="17fa8-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
- <span data-ttu-id="17fa8-107">内部状態と外部動作の間の (クライアントとサーバーの両方での) 強力なカプセル化。</span><span class="sxs-lookup"><span data-stu-id="17fa8-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
- <span data-ttu-id="17fa8-108">他の関連するサーバー機能との緊密な統合。</span><span class="sxs-lookup"><span data-stu-id="17fa8-108">Deep integration with other related server features.</span></span> <span data-ttu-id="17fa8-109">独自の UDT を定義すると、列定義、変数、パラメーター、関数の結果、カーソル、トリガー、およびレプリケーションなど、SQL Server のシステム型を利用できるすべてのコンテキストでその UDT を使用できます。</span><span class="sxs-lookup"><span data-stu-id="17fa8-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="17fa8-110">詳細については、ご使用中の SQL Server のバージョンに対応する [SQL Server ドキュメント](/sql)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17fa8-110">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="17fa8-111">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="17fa8-111">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="17fa8-112">CLR ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="17fa8-112">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="17fa8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="17fa8-113">See also</span></span>

- [<span data-ttu-id="17fa8-114">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="17fa8-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
