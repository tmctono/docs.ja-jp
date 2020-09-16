---
title: FileName で指定されたファイルは、正しい XML ファイルではありません
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 7d9500e58044f52a4e2508c9cb23a0e8186bc08d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553897"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>FileName で指定されたファイルは、正しい XML ファイルではありません

指定したファイル名は、正しい XML ファイルではありません。 XML ドキュメントの許可されている構造体とコンテンツを指定する場合、ドキュメント型定義 (DTD)、Microsoft XML-Data Reduced (XDR) スキーマ、または XML スキーマ定義言語 (XSD) スキーマを使用できます。 .NET Framework で XML 文法を指定する場合は、XSD スキーマを使用することをお勧めします。

> [!NOTE]
> Visual Studio の以前のバージョンにある **XML デザイナー** とは、型指定されたデータセットおよび XML スキーマのデザイナーのことです。 **XML デザイナー** は、XML スキーマ ファイルの作成と編集に今も使用できます。 ただし、Visual Studio 2012 では、型指定されたデータセットを作成および編集するためのデザイナーが **データセットデザイナー**です。 詳細については、「型指定された [データセットの作成と編集](/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120))」を参照してください。

## <a name="to-correct-this-error"></a>このエラーを解決するには

- 正しいファイル名を指定していることを確認します。

- 確認する必要のある XML ファイルを **XML デザイナー**に読み込んで、指定したファイルに正しい XML が含まれていることを確認します。 **[XML]** メニューで、 **[XML の整合性チェック]** をクリックします。 エラーは **[タスク一覧]** に表示されます。

- XML ファイルに関連付けられた XML スキーマがある場合は、定義された構造体にその要素が出現し、個々の要素のコンテンツがスキーマで指定された宣言されたデータ型に準拠していることを確認します。

## <a name="see-also"></a>関連項目

- <xref:System.Xml>
- [方法: ファイル パスを解析する](../developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
