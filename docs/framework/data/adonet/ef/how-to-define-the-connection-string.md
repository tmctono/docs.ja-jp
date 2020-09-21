---
title: '方法: 接続文字列を定義する'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9b029644e0d4e4c7467fbe1e1144579e6edb3478
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536211"
---
# <a name="how-to-define-the-connection-string"></a>方法: 接続文字列を定義する

このトピックでは、概念モデルに接続するための接続文字列を定義する方法について説明します。 このトピックは、[AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) の概念モデルが基になっています。 AdventureWorks Sales Model は、Entity Framework ドキュメントのタスク関連のトピック全般で使用されます。 このトピックでは、Entity Framework の構成が済んでいること、および AdventureWorks Sales Model が定義済みであることを前提としています。 詳細については、[モデル ファイルとマッピング ファイルを手動で定義する](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))」を参照してください。 このトピックの手順は、「[方法: Entity Framework プロジェクトを手動で構成する](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))」にも含まれます。

> [!NOTE]
> Visual Studio プロジェクトで Entity Data Model ウィザードを使用した場合、自動的に .edmx ファイルが生成され、Entity Framework を使用するようにプロジェクトが構成されます。 詳細については、[Entity Data Model ウィザードを使用する](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))」を参照してください。

## <a name="to-define-the-entity-framework-connection-string"></a>Entity Framework 接続文字列を定義するには

- プロジェクトのアプリケーション構成ファイル (app.config) を開き、次の接続文字列を追加します。

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

プロジェクトにアプリケーション構成ファイルが存在しない場合は、 **[プロジェクト]** メニューの **[新しい項目の追加]** を選択し、 **[全般]** カテゴリの **[アプリケーション構成ファイル]** を選択して、 **[追加]** をクリックすることによって追加できます。

## <a name="see-also"></a>関連項目

- [クイック スタート](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [方法: 新しい .edmx ファイルを作成する](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [ADO.NET Entity Data Model ツール](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
