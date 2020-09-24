---
title: ログのストリームを取得できません
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 887356fac3abe5c9d28751f7c4d3b1908ed35acb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078386"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a>ログのストリームを取得できません

ログのストリームを取得できません。 に基づく可能性のあるファイル名 \<name> は既に使用されています。  
  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>に基づく可能性のあるすべてのログファイル名 \<name> が既に使用されているため、クラスで新しいログファイルを作成できませんでした。  
  
 ログ ファイルが多すぎる場合、アプリケーションにアーキテクチャの問題がある可能性があります。 詳細については、 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> クラスのドキュメントを参照してください。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1. <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> プロパティを <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> または <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> に設定して、ログ ファイル名に日付スタンプを含めます。  
  
2. 既存のログをアーカイブし、それらをコンピューターから削除して、 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> オブジェクトが新しいログを作成できるようにします。  
  
## <a name="see-also"></a>こちらもご覧ください

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [[DirectoryPath]](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
