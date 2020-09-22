---
title: '方法: COM から .NET 型を参照する'
description: COM から .NET 型を参照します。 VB クライアントはオブジェクト ブラウザーで .NET オブジェクトを表示できますが、C++ クライアントは \#import ディレクティブを使用して TLB ファイルを参照する必要があります。
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: fad0a8163bd3d023911fd8554a77f740ac010ee6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547246"
---
# <a name="how-to-reference-net-types-from-com"></a>方法: COM から .NET 型を参照する
クライアント アンド サーバー コードの観点からすると、COM と .NET Framework の違いはほとんどわかりません。 Microsoft Visual Basic クライアントでは、オブジェクト ブラウザーを使って .NET オブジェクトを表示できます。オブジェクト ブラウザーには、オブジェクトのメソッドと構文、プロパティ、およびフィールドが、他の COM オブジェクトの場合と同様に公開されます。  
  
 タイプ ライブラリのインポート処理は、COM タイプ ライブラリにメタデータをエクスポートする場合と同じツールを使用しますが、C++ クライアントの場合の方がやや複雑です。 アンマネージ C++ クライアントから .NET オブジェクトのメンバーを参照するには、 **#import** ディレクティブが含まれている TLB ファイル (Tlbexp.exe により生成) を参照します。 C++ からタイプ ライブラリを参照する場合は、**raw_interfaces_only** オプションを指定するか、または基本クラス ライブラリの Mscorlib.tlb 内の定義をインポートする必要があります。  
  
### <a name="to-import-a-library"></a>ライブラリをインポートするには  
  
- **#import** ディレクティブで **raw_interfaces_only** オプションを指定します。 次に例を示します。  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     \- または -  
  
- Mscorlib.tlb の #import ディレクティブを含めます。 次に例を示します。  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a>関連項目

- [COM への .NET Framework コンポーネントの公開](exposing-dotnet-components-to-com.md)
- [COM へのアセンブリの登録](registering-assemblies-with-com.md)
- [.NET オブジェクトの呼び出し](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [COM アクセスに対するアプリケーションの配置](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
