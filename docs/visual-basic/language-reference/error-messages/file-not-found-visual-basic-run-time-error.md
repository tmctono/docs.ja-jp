---
title: ファイルが見つかりません。(Visual Basic ランタイム エラー)
ms.date: 07/20/2015
f1_keywords:
- vbrID53
ms.assetid: 57addb16-6f9a-444d-8af8-dda52431daca
ms.openlocfilehash: 6c65ca7f41af48f9fc8e60634815be1a615c561b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160725"
---
# <a name="file-not-found-visual-basic-run-time-error"></a><span data-ttu-id="8e95b-102">ファイルが見つかりません。(Visual Basic ランタイム エラー)</span><span class="sxs-lookup"><span data-stu-id="8e95b-102">File not found (Visual Basic Run-Time Error)</span></span>

<span data-ttu-id="8e95b-103">指定された場所でファイルが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8e95b-103">The file was not found where specified.</span></span> <span data-ttu-id="8e95b-104">このエラーには、次のような原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="8e95b-104">The error has the following possible causes:</span></span>

- <span data-ttu-id="8e95b-105">ステートメントが、存在しないファイルを参照しています。</span><span class="sxs-lookup"><span data-stu-id="8e95b-105">A statement refers to a file that does not exist.</span></span>

- <span data-ttu-id="8e95b-106">ダイナミック リンク ライブラリ (DLL) でプロシージャを呼び出そうとしましたが、`Declare` ステートメントの `Lib` 句で指定されたライブラリが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8e95b-106">An attempt was made to call a procedure in a dynamic-link library (DLL), but the library specified in the `Lib` clause of the `Declare` statement cannot be found.</span></span>

- <span data-ttu-id="8e95b-107">プロジェクトを開こうとしたか、存在しないテキスト ファイルを読み込もうとしました。</span><span class="sxs-lookup"><span data-stu-id="8e95b-107">You attempted to open a project or load a text file that does not exist.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8e95b-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="8e95b-108">To correct this error</span></span>

- <span data-ttu-id="8e95b-109">ファイル名とパスの指定のスペルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e95b-109">Check the spelling of the file name and the path specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e95b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e95b-110">See also</span></span>

- [<span data-ttu-id="8e95b-111">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="8e95b-111">Declare Statement</span></span>](../statements/declare-statement.md)
