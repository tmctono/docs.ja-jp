---
title: '方法: 文字列を Visual Basic でバイト配列に変換します。'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 2fa0b86459e6191d3bd5f884d92b071218b4063a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938308"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="4095a-102">方法: 文字列を Visual Basic でバイト配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="4095a-102">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>
<span data-ttu-id="4095a-103">このトピックでは、文字列をバイト配列に変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4095a-103">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4095a-104">例</span><span class="sxs-lookup"><span data-stu-id="4095a-104">Example</span></span>  
 <span data-ttu-id="4095a-105">この例では、<xref:System.Text.Encoding.GetBytes%2A>のメソッド、<xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>エンコーディングのバイト配列に文字列に変換するクラス。</span><span class="sxs-lookup"><span data-stu-id="4095a-105">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 <span data-ttu-id="4095a-106">バイト配列に文字列に変換するいくつかのエンコード オプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="4095a-106">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
- <span data-ttu-id="4095a-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>:ASCII (7 ビット) 文字セットのエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="4095a-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="4095a-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>:ビッグ エンディアン バイト順を使用する utf-16 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="4095a-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="4095a-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>:システムの現在の ANSI コード ページのエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="4095a-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="4095a-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>:リトル エンディアン バイト順を使用する utf-16 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="4095a-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="4095a-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>:リトル エンディアン バイト順を使用する utf-32 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="4095a-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="4095a-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>:UTF-7 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="4095a-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="4095a-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>:UTF-8 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="4095a-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4095a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4095a-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [<span data-ttu-id="4095a-115">方法: Visual Basic で文字列のバイト配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="4095a-115">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
