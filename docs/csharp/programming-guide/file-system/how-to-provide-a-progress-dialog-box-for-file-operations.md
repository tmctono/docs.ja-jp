---
title: ファイル操作の [進行状況] ダイアログ ボックスを表示する方法 - C# プログラミング ガイド
description: CopyFile (String, String, UIOption) メソッドを使用して、ファイル操作の [進行状況] ダイアログ ボックスを表示する方法について説明します。
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 5d16aeb3a5394ca250e4a5e26074db797c54216d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185887"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a>ファイル操作の [進行状況] ダイアログ ボックスを表示する方法 (C# プログラミング ガイド)

<xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> 名前空間の <xref:Microsoft.VisualBasic?displayProperty=nameWithType> メソッドを使用すると、Windows でのファイル操作に関する進行状況を示す標準ダイアログ ボックスを提供できます。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a>Visual Studio で参照を追加するには  
  
1. メニュー バーで、 **[プロジェクト]** 、 **[参照の追加]** の順に選択します。  
  
     **[参照マネージャー]** ダイアログ ボックスが表示されます。  
  
2. **[アセンブリ]** で、 **[フレームワーク]** を選択します (選択されていない場合)。  
  
3. 名前の一覧で、 **[Microsoft.VisualBasic]** のチェック ボックスをオンにし、 **[OK]** をクリックしてダイアログ ボックスを閉じます。  
  
## <a name="example"></a>例  

 次のコードは、`sourcePath` で指定されたディレクトリを `destinationPath` で指定されたディレクトリにコピーします。 また、操作の完了までに必要な残りの予測時間を示す、標準的なダイアログ ボックスを表示します。  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a>関連項目

- [ファイル システムとレジストリ (C# プログラミング ガイド)](./index.md)
