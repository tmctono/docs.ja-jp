---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: a4c5e7db813089d1dd138416ac54dd4be467b87b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355020"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="f3249-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="f3249-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="f3249-103">同じリストを反復処理するため、現在の列挙子と同じ状態の別の未加工入力デバイスの列挙子を作成します。</span><span class="sxs-lookup"><span data-stu-id="f3249-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3249-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3249-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3249-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3249-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="f3249-106">[out]受け取る出力変数のアドレス、 [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)インターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="f3249-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="f3249-107">メソッドが成功した場合は、この output 変数の値が定義されていません。</span><span class="sxs-lookup"><span data-stu-id="f3249-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f3249-108">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="f3249-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f3249-109">HRESULT:このメソッドでは、標準の戻り値 E_INVALIDARG、E_UNEXPECTED、E_OUTOFMEMORY をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f3249-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3249-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3249-110">Remarks</span></span>  
 <span data-ttu-id="f3249-111">このメソッドでは、後でそのポイントに返すために列挙体シーケンス内のポイントを録音することです。</span><span class="sxs-lookup"><span data-stu-id="f3249-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="f3249-112">呼び出し元は、最初の列挙子から個別にこの新しい列挙子を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3249-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
