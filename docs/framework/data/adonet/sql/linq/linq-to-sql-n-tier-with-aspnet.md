---
title: ASP.NET での LINQ to SQL N 層
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: a184c9dcb29e7994aefa4062be2b30484539c4e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175318"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>ASP.NET での LINQ to SQL N 層

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] が使われる ASP.NET アプリケーションでは、<xref:System.Web.UI.WebControls.LinqDataSource> Web サーバー コントロールを使用します。 コントロールでは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] に対するクエリの実行、ブラウザーへのデータ送信、データの取得、データベースを更新する [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の <xref:System.Data.Linq.DataContext> へのデータ送信などを行う必要があるロジックのほとんどが処理されます。 マークアップでこのコントロールを構成するだけで、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] とブラウザーの間のすべてのデータ転送をコントロールが処理するようになります。 コントロールによってプレゼンテーション層との対話が処理され、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によってデータ層との通信が処理されるため、開発者が ASP.NET の多層アプリケーションで主に注目するのは、カスタム ビジネス ロジックの作成になります。  
  
 `LINQDataSource` について詳しくは、「[LinqDataSource Web サーバー コントロールの概要](/previous-versions/aspnet/bb547113(v=vs.100))」をご覧ください。  
  
## <a name="see-also"></a>関連項目

- [LINQ to SQL を使用する n 層アプリケーションとリモート アプリケーション](n-tier-and-remote-applications-with-linq-to-sql.md)
