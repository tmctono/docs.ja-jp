---
title: AspNetCompatibilityRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 00908a39-a21b-4029-bbb9-33e5a6ed25a7
ms.openlocfilehash: 5b11aedc3069b80df40e36949e009dc902680889
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609448"
---
# <a name="aspnetcompatibilityrequirementsattribute"></a>AspNetCompatibilityRequirementsAttribute
AspNetCompatibilityRequirementsAttribute  
  
## <a name="syntax"></a>構文  
  
```csharp
class AspNetCompatibilityRequirementsAttribute : Behavior  
{  
  string RequirementsMode;  
};  
```  
  
## <a name="methods"></a>メソッド  
 AspNetCompatibilityRequirementsAttribute クラスは、メソッドをすべて定義しません。  
  
## <a name="properties"></a>プロパティ  
 AspNetCompatibilityRequirementsAttribute クラスには、次のプロパティがあります。  
  
### <a name="requirementsmode"></a>RequirementsMode  
 データ型: 文字列  
  
 アクセスの種類: 読み取り専用  
  
 ASP.NET 互換モードがアクティブかどうかを示します。  
  
## <a name="requirements"></a>必要条件  
  
|MOF|Servicemodel.mof にて宣言済み。|  
|---------|-----------------------------------|  
|名前空間|root\ServiceModel で定義|  
  
## <a name="see-also"></a>関連項目

- <xref:System.ServiceModel.ServiceHostingEnvironment.AspNetCompatibilityEnabled%2A>
