---
title: EmitAssemblyCustomAttribute メソッド
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77d54f6c8f67dda5132518d1fbd579a91ce82071
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777442"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="606df-102">EmitAssemblyCustomAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="606df-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="606df-103">を呼び出して、アセンブリレベルのカスタム属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="606df-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="606df-104">構文</span><span class="sxs-lookup"><span data-stu-id="606df-104">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="606df-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="606df-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="606df-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="606df-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="606df-107">属性をなするファイル。</span><span class="sxs-lookup"><span data-stu-id="606df-107">File that defiles the attribute.</span></span> <span data-ttu-id="606df-108">がバインドされ`AssemblyID`ていない .netmodule を示していない場合は、NULL にすることができます。</span><span class="sxs-lookup"><span data-stu-id="606df-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="606df-109">カスタム属性の型。</span><span class="sxs-lookup"><span data-stu-id="606df-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="606df-110">カスタム値データ。</span><span class="sxs-lookup"><span data-stu-id="606df-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="606df-111">カスタム値データの長さ。</span><span class="sxs-lookup"><span data-stu-id="606df-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="606df-112">カスタム属性がアセンブリ署名に関連付けられている場合は TRUE。</span><span class="sxs-lookup"><span data-stu-id="606df-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="606df-113">複数の属性を出力する場合は TRUE。</span><span class="sxs-lookup"><span data-stu-id="606df-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="606df-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="606df-114">Return Value</span></span>  
 <span data-ttu-id="606df-115">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="606df-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="606df-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="606df-116">Requirements</span></span>  
 <span data-ttu-id="606df-117">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="606df-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="606df-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="606df-118">See also</span></span>

- [<span data-ttu-id="606df-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="606df-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="606df-120">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="606df-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="606df-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="606df-121">ALink API</span></span>](index.md)
