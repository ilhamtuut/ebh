<template>
  <ul class="menu-nav">
    <router-link
      to="/dashboard"
      v-slot="{ href, navigate, isActive, isExactActive }"
    >
      <li
        aria-haspopup="true"
        data-menu-toggle="hover"
        class="menu-item"
        :class="[
          isActive && 'menu-item-active',
          isExactActive && 'menu-item-active'
        ]"
      >
        <a :href="href" class="menu-link" @click="navigate">
          <i class="menu-icon flaticon2-architecture-and-city"></i>
          <span class="menu-text">Dashboard</span>
        </a>
      </li>
    </router-link>

    <li class="menu-section">
      <h4 class="menu-text">Main Menu</h4>
      <i class="menu-icon flaticon-more-v2"></i>
    </li>

    <li
      aria-haspopup="true"
      data-menu-toggle="hover"
      class="menu-item menu-item-submenu"
      v-bind:class="{ 'menu-item-open': hasActiveChildren('/user') }"
    >
      <a href="#" class="menu-link menu-toggle">
        <i class="menu-icon flaticon2-digital-marketing"></i>
        <span class="menu-text">Applications</span>
        <i class="menu-arrow"></i>
      </a>
      <div class="menu-submenu">
        <span class="menu-arrow"></span>
        <ul class="menu-subnav">
          <li aria-haspopup="true" class="menu-item menu-item-parent">
            <span class="menu-link">
              <span class="menu-text">Applications</span>
            </span>
          </li>

          <router-link
            to="/user/profile"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Profile</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/user/inbox"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Inbox</span>
              </a>
            </li>
          </router-link>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/user')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Users</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/user/add"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Add User</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/user/list"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">List User</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>
          
        </ul>
      </div>
    </li>

    <li
      aria-haspopup="true"
      data-menu-toggle="hover"
      class="menu-item menu-item-submenu"
      v-bind:class="{
        'menu-item-open': hasActiveChildren('/human')
      }"
    >
      <a href="#" class="menu-link menu-toggle">
        <i class="menu-icon flaticon-users-1"></i>
        <span class="menu-text">Human Resources</span>
        <i class="menu-arrow"></i>
      </a>
      <div class="menu-submenu">
        <span class="menu-arrow"></span>
        <ul class="menu-subnav">
          <li aria-haspopup="true" class="menu-item menu-item-parent">
            <span class="menu-link">
              <span class="menu-text">Human Resources</span>
            </span>
          </li>

          <router-link
            to="/human/employee"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Data Karyawan</span>
              </a>
            </li>
          </router-link>

        </ul>
      </div>
    </li>

    <li
      aria-haspopup="true"
      data-menu-toggle="hover"
      class="menu-item menu-item-submenu"
      v-bind:class="{
        'menu-item-open': hasActiveChildren('/purchase')
      }"
    >
      <a href="#" class="menu-link menu-toggle">
        <i class="menu-icon flaticon-file-2"></i>
        <span class="menu-text">Purchasing</span>
        <i class="menu-arrow"></i>
      </a>
      <div class="menu-submenu">
        <span class="menu-arrow"></span>
        <ul class="menu-subnav">
          <li aria-haspopup="true" class="menu-item menu-item-parent">
            <span class="menu-link">
              <span class="menu-text">Purchasing</span>
            </span>
          </li>

          <router-link
            to="/purchase/request"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Permintaan Pembelian</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/purchase/order"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Order Pembelian</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/purchase/description"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Uraian Pembelian</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/purchase/approv"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Approval Pembelian</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/purchase/release"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Release Order Pembelian</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/purchase/close/order"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Penutupan Order Pembelian</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/purchase/request/order"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Penutupan Permintaan Pembelian</span>
              </a>
            </li>
          </router-link>
        </ul>
      </div>
    </li>

    <li class="menu-section">
      <h4 class="menu-text">Components</h4>
      <i class="menu-icon flaticon-more-v2"></i>
    </li>

    <li
      aria-haspopup="true"
      data-menu-toggle="hover"
      class="menu-item menu-item-submenu"
      v-bind:class="{ 'menu-item-open': hasActiveChildren('/vue-bootstrap') }"
    >
      <a href="#" class="menu-link menu-toggle">
        <i class="menu-icon flaticon2-digital-marketing"></i>
        <span class="menu-text">Vue Bootstrap</span>
        <i class="menu-arrow"></i>
      </a>
      <div class="menu-submenu">
        <span class="menu-arrow"></span>
        <ul class="menu-subnav">
          <li aria-haspopup="true" class="menu-item menu-item-parent">
            <span class="menu-link">
              <span class="menu-text">Vue Bootstrap</span>
            </span>
          </li>

          <router-link
            to="/vue-bootstrap/alert"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Alert</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/badge"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Badge</span>
              </a>
            </li>
          </router-link>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/vue-bootstrap/button')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Buttons</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/vue-bootstrap/button"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Button</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/button-group"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Button Group</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/button-toolbar"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Button Toolbar</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>

          <router-link
            to="/vue-bootstrap/card"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Card</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/carousel"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Carousel</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/collapse"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Collapse</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/dropdown"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Dropdown</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/embed"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Embed</span>
              </a>
            </li>
          </router-link>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/vue-bootstrap/form')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Form</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/vue-bootstrap/form"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Form</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/form-checkbox"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Form Checkbox</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/form-file"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Form File</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/form-group"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Form Group</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/form-input"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Form Input</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/form-radio"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Form Radio</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/form-select"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Form Select</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/form-textarea"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Form Textarea</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>

          <router-link
            to="/vue-bootstrap/image"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Image</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/input-group"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Input Group</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/jumbotron"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Jumbotron</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/layout-grid-system"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Layout and Grid System</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/link"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Link</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/list-group"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">List group</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/media"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Media</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/modal"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Modal</span>
              </a>
            </li>
          </router-link>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/vue-bootstrap/nav')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Navigation</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/vue-bootstrap/nav"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Nav</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/navbar"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Navbar</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/vue-bootstrap/pagination')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Pagination</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/vue-bootstrap/pagination"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Pagination</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/pagination-nav"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Pagination Nav</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/vue-bootstrap/notify')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Notify</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/vue-bootstrap/notify-popover"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Popover</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/notify-toasts"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Toasts</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/notify-tooltip"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Tooltip</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/vue-bootstrap/progress')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Progress</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/vue-bootstrap/progress"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Progress</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vue-bootstrap/progress-spinner"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Spinner</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>

          <router-link
            to="/vue-bootstrap/table"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Table</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vue-bootstrap/tabs"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Tabs</span>
              </a>
            </li>
          </router-link>
        </ul>
      </div>
    </li>

    <li
      aria-haspopup="true"
      data-menu-toggle="hover"
      class="menu-item menu-item-submenu"
      v-bind:class="{ 'menu-item-open': hasActiveChildren('vuetify') }"
    >
      <a href="#" class="menu-link menu-toggle">
        <i class="menu-icon flaticon-web"></i>
        <span class="menu-text">Vuetify</span>
        <i class="menu-arrow"></i>
      </a>
      <div class="menu-submenu">
        <span class="menu-arrow"></span>
        <ul class="menu-subnav">
          <li aria-haspopup="true" class="menu-item menu-item-parent">
            <span class="menu-link">
              <span class="menu-text">Vuetify</span>
            </span>
          </li>

          <router-link
            to="/vuetify/alerts"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Alerts</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/avatars"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Avatars</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/badges"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Badges</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/buttons"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Buttons</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/calendars"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Calendars</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/cards"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Cards</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/chips"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Chips</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/dialog"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Dialog</span>
              </a>
            </li>
          </router-link>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/vuetify/forms')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Forms</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/vuetify/forms-autocompletes"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Autocompletes</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/forms-file-inputs"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">File Inputs</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/forms"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Forms</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/forms-selection-controls"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Selection Controls</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/forms-selects"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Selects</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/forms-textareas"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Textareas</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/forms-text-fields"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Text Fields</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>

          <li
            aria-haspopup="true"
            data-menu-toggle="hover"
            class="menu-item menu-item-submenu"
            v-bind:class="{
              'menu-item-open': hasActiveChildren('/vuetify/tables')
            }"
          >
            <a href="#" class="menu-link menu-toggle">
              <i class="menu-bullet menu-bullet-dot">
                <span></span>
              </i>
              <span class="menu-text">Tables</span>
              <i class="menu-arrow"></i>
            </a>
            <div class="menu-submenu">
              <span class="menu-arrow"></span>
              <ul class="menu-subnav">
                <li aria-haspopup="true" class="menu-item menu-item-parent">
                  <span class="menu-link">
                    <span class="menu-text"></span>
                  </span>
                </li>

                <router-link
                  to="/vuetify/tables-simple-tables"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Simple Tables</span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/tables-data-tables"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    data-menu-toggle="hover"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot">
                        <span></span>
                      </i>
                      <span class="menu-text">Data Tables</span>
                    </a>
                  </li>
                </router-link>
              </ul>
            </div>
          </li>

          <router-link
            to="/vuetify/tabs"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Tabs</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/timelines"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Timelines</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/tooltips"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Tooltips</span>
              </a>
            </li>
          </router-link>

          <router-link
            to="/vuetify/treeview"
            v-slot="{ href, navigate, isActive, isExactActive }"
          >
            <li
              aria-haspopup="true"
              data-menu-toggle="hover"
              class="menu-item"
              :class="[
                isActive && 'menu-item-active',
                isExactActive && 'menu-item-active'
              ]"
            >
              <a :href="href" class="menu-link" @click="navigate">
                <i class="menu-bullet menu-bullet-dot">
                  <span></span>
                </i>
                <span class="menu-text">Treeview</span>
              </a>
            </li>
          </router-link>
        </ul>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  name: "KTMenu",
  methods: {
    hasActiveChildren(match) {
      return this.$route["path"].indexOf(match) !== -1;
    }
  }
};
</script>
