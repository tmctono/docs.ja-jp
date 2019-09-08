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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d696326ff8861ed8496474f76e9eaf89b4ead3e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795390"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="6681f-102">CreateInstallReferenceEnum 関数</span><span class="sxs-lookup"><span data-stu-id="6681f-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="6681f-103">指定したアセンブリへのアプリケーションの参照のリストを表す[Iinstallreferenceenum](iinstallreferenceenum-interface.md)インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6681f-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6681f-104">構文</span><span class="sxs-lookup"><span data-stu-id="6681f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6681f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6681f-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="6681f-106">入出力返され`IInstallReferenceEnum`たポインター。</span><span class="sxs-lookup"><span data-stu-id="6681f-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="6681f-107">から参照を列挙する対象のアセンブリを識別する[IAssemblyName](iassemblyname-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="6681f-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6681f-108">から列挙子の動作に影響を与えるフラグ。</span><span class="sxs-lookup"><span data-stu-id="6681f-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6681f-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="6681f-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="6681f-110">`pvReserved`null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6681f-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6681f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6681f-111">Requirements</span></span>  
 <span data-ttu-id="6681f-112">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6681f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6681f-113">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6681f-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6681f-114">**ライブラリ**Fusion .dll と Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="6681f-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="6681f-115">Mscorwks.dll の代わりに Fusion を使用して、正しいバージョンの .NET Framework を対象としていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6681f-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="6681f-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6681f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6681f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6681f-117">See also</span></span>

- [<span data-ttu-id="6681f-118">IInstallReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6681f-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="6681f-119">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6681f-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="6681f-120">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="6681f-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
