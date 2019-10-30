---
title: CreateInstallReferenceEnum 関数
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: f089769f854bad5d3e572e0307734e06e72ca89c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108566"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="a850a-102">CreateInstallReferenceEnum 関数</span><span class="sxs-lookup"><span data-stu-id="a850a-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="a850a-103">指定したアセンブリへのアプリケーションの参照のリストを表す[Iinstallreferenceenum](iinstallreferenceenum-interface.md)インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a850a-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a850a-104">構文</span><span class="sxs-lookup"><span data-stu-id="a850a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a850a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a850a-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="a850a-106">入出力返された `IInstallReferenceEnum` ポインター。</span><span class="sxs-lookup"><span data-stu-id="a850a-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="a850a-107">から参照を列挙する対象のアセンブリを識別する[IAssemblyName](iassemblyname-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="a850a-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a850a-108">から列挙子の動作に影響を与えるフラグ。</span><span class="sxs-lookup"><span data-stu-id="a850a-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a850a-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="a850a-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a850a-110">`pvReserved` は null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a850a-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a850a-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="a850a-111">Requirements</span></span>  
 <span data-ttu-id="a850a-112">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a850a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a850a-113">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a850a-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a850a-114">**ライブラリ:** Fusion .dll と Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="a850a-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="a850a-115">Mscorwks.dll の代わりに Fusion を使用して、正しいバージョンの .NET Framework を対象としていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a850a-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a850a-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a850a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a850a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a850a-117">See also</span></span>

- [<span data-ttu-id="a850a-118">IInstallReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a850a-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="a850a-119">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a850a-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="a850a-120">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="a850a-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
