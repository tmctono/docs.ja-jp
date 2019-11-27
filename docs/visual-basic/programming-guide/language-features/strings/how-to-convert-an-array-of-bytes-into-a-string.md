---
title: '方法: バイト配列を文字列に変換する'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 8c1d9d1d2e89390873bc1c3dbb9623f047433a9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351987"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="9bd01-102">方法 : Visual Basic でバイトの配列を文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="9bd01-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="9bd01-103">このトピックでは、バイト配列のバイトを文字列に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bd01-104">例</span><span class="sxs-lookup"><span data-stu-id="9bd01-104">Example</span></span>  
 <span data-ttu-id="9bd01-105">この例では、<xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding クラスの <xref:System.Text.Encoding.GetString%2A> メソッドを使用して、バイト配列のすべてのバイトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 <span data-ttu-id="9bd01-106">複数のエンコードオプションから選択して、バイト配列を文字列に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="9bd01-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
- <span data-ttu-id="9bd01-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: ASCII (7 ビット) 文字セットのエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="9bd01-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: ビッグエンディアンのバイト順を使用する UTF-16 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="9bd01-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: システムの現在の ANSI コードページのエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="9bd01-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: リトルエンディアンのバイト順を使用する UTF-16 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="9bd01-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: リトルエンディアンのバイト順を使用して、32形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="9bd01-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: UTF-7 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="9bd01-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: UTF-8 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="9bd01-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd01-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bd01-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="9bd01-115">方法: Visual Basic で文字列をバイト配列に変換する</span><span class="sxs-lookup"><span data-stu-id="9bd01-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
