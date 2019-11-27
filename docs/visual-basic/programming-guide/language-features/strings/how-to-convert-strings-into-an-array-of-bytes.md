---
title: '方法: 文字列をバイト配列に変換する'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 76fde3120ce629ce32f29ca28d90eba24fff726c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351968"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="f34dc-102">方法 : Visual Basic で文字列をバイトの配列に変換する</span><span class="sxs-lookup"><span data-stu-id="f34dc-102">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>
<span data-ttu-id="f34dc-103">このトピックでは、文字列をバイト配列に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-103">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f34dc-104">例</span><span class="sxs-lookup"><span data-stu-id="f34dc-104">Example</span></span>  
 <span data-ttu-id="f34dc-105">この例では、<xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding クラスの <xref:System.Text.Encoding.GetBytes%2A> メソッドを使用して、文字列をバイト配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-105">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 <span data-ttu-id="f34dc-106">文字列をバイト配列に変換するには、いくつかのエンコードオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="f34dc-106">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
- <span data-ttu-id="f34dc-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: ASCII (7 ビット) 文字セットのエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="f34dc-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: ビッグエンディアンのバイト順を使用する UTF-16 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="f34dc-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: システムの現在の ANSI コードページのエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="f34dc-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: リトルエンディアンのバイト順を使用する UTF-16 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="f34dc-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: リトルエンディアンのバイト順を使用して、32形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="f34dc-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: UTF-7 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="f34dc-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: UTF-8 形式のエンコーディングを取得します。</span><span class="sxs-lookup"><span data-stu-id="f34dc-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f34dc-114">参照</span><span class="sxs-lookup"><span data-stu-id="f34dc-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [<span data-ttu-id="f34dc-115">方法: Visual Basic でバイト配列を文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="f34dc-115">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
