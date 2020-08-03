---
title: '軽減策: パスのコロン チェック'
description: 適切なドライブ区切り構文 (コロン) のチェックをサポートする目的で .NET Framework 4.6.2 で行われた変更について説明します。
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: f32ee54f88bc4747fd0d8065b0dce06b151d1d9a
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475451"
---
# <a name="mitigation-path-colon-checks"></a>軽減策:パスのコロン チェック
.NET Framework 4.6.2 以降を対象とするアプリから、以前はサポートされていなかったパスをサポートするために (長さと形式の両方について) 数多くの変更が加えられました。 具体的には、適切なドライブの区切り構文 (コロン) のチェックがより正しく行われるようになりました。  
  
## <a name="impact"></a>影響  
 これらの変更は、以前は <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> メソッドと <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> メソッドでサポートされていた一部の URI のパスをブロックします。  
  
## <a name="mitigation"></a>軽減策  
 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> メソッドや <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> メソッドでサポートされなくなった、以前は受け入れられていたパスの問題を回避するには、次のようにします。  
  
- URL からスキームを手動で削除します。 たとえば、URL から `file://` を削除します。  
  
- <xref:System.Uri> コンストラクターに URI を渡し、<xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> プロパティの値を取得します。  
  
- `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> を `true` に切り替えて、新しいパスの正規化を無効にします。  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
    </runtime>  
    ```  
  
## <a name="see-also"></a>関連項目

- [アプリケーションの互換性](application-compatibility.md)
