---
title: '方法: 16 進文字列を数値に変換する'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347172"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="f6208-102">方法: 16 進数文字列を数値に変換する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6208-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>

<span data-ttu-id="f6208-103">この例では、<xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> メソッドを使用して、16 進数文字列を整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="f6208-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="f6208-104">16 進数文字列を数値に変換するには</span><span class="sxs-lookup"><span data-stu-id="f6208-104">To convert a hexadecimal string to a number</span></span>

- <span data-ttu-id="f6208-105"><xref:System.Convert.ToInt32(System.String,System.Int32)> メソッドを使用して、base 16 で表された数値を整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="f6208-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>

  <span data-ttu-id="f6208-106"><xref:System.Convert.ToInt32(System.String,System.Int32)> メソッドの最初の引数は、変換する文字列です。</span><span class="sxs-lookup"><span data-stu-id="f6208-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="f6208-107">2 番目の引数は、数値をどの基数で表すかを示しています。16 進数は base 16 です。</span><span class="sxs-lookup"><span data-stu-id="f6208-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- <span data-ttu-id="f6208-108">16 進数文字列には次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="f6208-108">Note that the hexadecimal string has the following restrictions:</span></span>

  - <span data-ttu-id="f6208-109">`&h` プレフィックスを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f6208-109">It cannot include the `&h` prefix.</span></span>
  - <span data-ttu-id="f6208-110">`_` 桁区切り記号を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f6208-110">It cannot include the `_` digit separator.</span></span>

  <span data-ttu-id="f6208-111">このプレフィックスまたは桁区切り記号が存在する場合、<xref:System.Convert.ToInt32(System.String,System.Int32)> メソッドの呼び出しは <xref:System.FormatException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="f6208-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6208-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6208-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
