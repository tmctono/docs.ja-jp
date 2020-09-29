---
title: '方法: EntityCommand を使用してパラメーター化されたストアド プロシージャを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: ec1ff7cdbdc83bc409b191f0aefe2b50cbad9225
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192166"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a>方法: EntityCommand を使用してパラメーター化されたストアド プロシージャを実行する

このトピックでは、<xref:System.Data.EntityClient.EntityCommand> クラスを使用して、パラメーター化されたストアド プロシージャを実行する方法を示します。  
  
### <a name="to-run-the-code-in-this-example"></a>この例のコードを実行するには  
  
1. [School モデル](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))をプロジェクトに追加し、Entity Framework が使用されるようにプロジェクトを構成します。 詳細については、[Entity Data Model ウィザードを使用する](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))」を参照してください。  
  
2. アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. `GetStudentGrades` ストアド プロシージャをインポートし、戻り値の型として `CourseGrade` エンティティを指定します。 ストアド プロシージャのインポート方法については、「[方法: ストアド プロシージャをインポートする](/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100))」をご覧ください。  
  
## <a name="example"></a>例  

 次のコードでは、`GetStudentGrades` ストアド プロシージャが実行されます。`StudentId` は必須パラメーターです。 結果は <xref:System.Data.EntityClient.EntityDataReader> によって読み取られます。  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a>関連項目

- [Entity Framework 用の EntityClient プロバイダー](entityclient-provider-for-the-entity-framework.md)
