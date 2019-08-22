---
title: クラス コンストラクター内のクラスの既定のインスタンスを使用すると、無限の再帰呼び出しを引き起こす能性があります。
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: cec3d3d462822ca571cab59a2e4d7e730d2aec46
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664368"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="60e40-102">クラス コンストラクター内のクラスの既定のインスタンスを使用すると、無限の再帰呼び出しを引き起こす能性があります。</span><span class="sxs-lookup"><span data-stu-id="60e40-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="60e40-103">クラスの既定のインスタンスは、クラス コンストラクターで使用されています。</span><span class="sxs-lookup"><span data-stu-id="60e40-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="60e40-104">これは、無限ループとも呼ばれる、無限の再帰呼び出しを引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60e40-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60e40-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="60e40-105">To correct this error</span></span>  
  
- <span data-ttu-id="60e40-106">クラス コンストラクターから、既定のインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="60e40-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60e40-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="60e40-107">See also</span></span>

- [<span data-ttu-id="60e40-108">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="60e40-108">Constructors</span></span>](../programming-guide/concepts/object-oriented-programming.md#constructors)
