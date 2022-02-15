<template>
  <div class="app-brand" id="app-brand">
        <span id="icon" class="icon">
          <svg width="24" height="24"
               fill="none"
               stroke="currentColor"
               stroke-width="2"
               stroke-linecap="round"
               stroke-linejoin="round">
             <path
                 d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7
                 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8
                 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z">

             </path>
          </svg>
        </span>
    <strong class="brand-name">My Messenger</strong>
    <button id="profile-btn" class="profile-btn" tabindex="1">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"
           stroke-linecap="round" stroke-linejoin="round">
        <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
        <circle cx="12" cy="7" r="4"></circle>
      </svg>
    </button>
  </div>
</template>

<script>
export default {}
</script>

<style>
.icon {
  height: 32px;
  width: 32px;
  background-color: green;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  color: #fff;
  margin-right: 1rem;
}

.icon:hover {
  cursor: pointer;
  background-color: #6abd6a;
}

.app-brand {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  padding-top: 15px;
}

.profile-btn {
  background: none;
  border: none;
  color: green;
}

.profile-btn:hover {
  background-color: #ece9e9;
  cursor: pointer;
}

.brand-name {
  user-select: none;
  font-size: 18px;
  color: rgba(12, 11, 11, 0.76);
}

.avatar-container {
  flex: 0 1 3.5em;
  width: 3.5em;
  height: 3.5em;
  margin-bottom: .75em;
  border-radius: 50%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #efefef;
  font-weight: bold;
  font-size: 1em;
  position: relative;
  border: 2px solid var(--primaryColor);
  box-shadow: 0 0 8px 2px rgba(0,0,0,0.16);
}
.avatar-container img {
  max-width: 100%;
  position: relative;
  z-index: 1;
}
.avatar-container .char-avatar {
  position: absolute;
  z-index: 0;
}
.details {
  flex: 0 1 100%;
  text-align: center;

}
#name {
  flex: 0 1 100%;
  position: relative;
  margin: 0 0 .3em 0;
  font-size: .9em;
  font-weight: 900;
}

.authed-user {
  --primaryColor:  #3AD07A;
  --hoverColor: #edfbf3;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  padding: 1.5em .75em;
  position: relative;
  transition: max-height 1s, all .3s;
  max-height: 500px;
  transform-origin: top;
  background-color: #fff;
}
</style>